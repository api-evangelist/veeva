---
name: veeva-authenticate-and-query
description: Authenticate to a Veeva Vault and read data with VQL, handling session lifetime, the Auth burst limit, and the Vault error envelope.
api: veeva:veeva-query-api
generated: '2026-08-15'
method: generated
operations:
  - authenticateUser
  - executeVQLQuery
  - listUsers
---

# Authenticate to Vault and run a VQL query

## Before you start

- Every call is scoped to ONE Vault. The base is `https://{vaultDNS}/api/{version}` — for example
  `https://myvault.veevavault.com/api/v26.2`. `{vaultDNS}` is the customer's own Vault host; there
  is no shared Veeva API host.
- Prefer an **API access token** over username/password. Token values start with `veeva-vault-`
  and go in `Authorization: Bearer <token>`. They are scoped to one Vault, capped at 25 active
  per user, and shown only once at creation.
- Use `authenticateUser` only when you have no token. It costs an Auth burst-limit slot.

## Steps

1. **(Token path)** Skip authentication entirely. Send
   `Authorization: Bearer veeva-vault-...` on every request.

2. **(Session path)** Call `authenticateUser` — `POST /auth` with
   `Content-Type: application/x-www-form-urlencoded` and `username`, `password`, optional
   `vaultDNS`. Read `sessionId` from the response and send it raw in the `Authorization`
   header (no `Bearer` prefix).
   - Inspect the returned `vaultIds[]` and confirm the `vaultId` you got is the Vault you
     wanted. If the requested `vaultDNS` is not accessible to that user, Vault silently issues
     a session for their *most relevant available* Vault instead of failing.
   - Sessions idle out after 20 minutes of inactivity. Reuse the session; do not re-authenticate
     per request.

3. **Query.** Call `executeVQLQuery` — `GET /query?q=<VQL>`. Page through the
   response-supplied next-page links rather than incrementing offsets by hand.

4. **Read the headers on every response.**
   - `X-VaultAPI-BurstLimitRemaining` — how much of the 5-minute window is left.
   - `X-VaultAPI-ResponseDelay` — present only when Vault has throttled you; it is a delay in
     milliseconds, not a rejection.
   - `X-VaultAPI-ExecutionId` — log it. Veeva Support asks for this value on any API ticket.

## Rules

- **There is no idempotency key.** Vault publishes no `Idempotency-Key` or equivalent. Do not
  blind-retry a write. `RACE_CONDITION` means another call is updating the same record.
- **Auth is limited separately.** The Auth burst limit is a 1-minute window keyed on
  `username` + `vaultDNS`. It starts delaying at 50% and then **fails** requests — unlike the
  general burst limit, which only delays. SAML/SSO and OAuth 2.0 / OIDC are exempt.
- **Branch on the numeric status code.** From 26R1.2 Vault returns `HTTP/1.1 200`, with no
  reason phrase. Never string-match `"OK"`.
- **Check the envelope, not just the status.** A 200 can still be a failure:
  `{"responseStatus":"FAILURE","errors":[{"type":"INVALID_SESSION_ID","message":"..."}]}`.
  Error types are listed in `errors/veeva-problem-types.yml`. `INVALID_SESSION_ID` means
  re-authenticate; `INCORRECT_QUERY_SYNTAX_ERROR` means fix the VQL, not retry it.
- **Identify yourself.** Send `X-VaultAPI-ClientID` in the documented form
  `{company}-{organization}-{component}-{server|client}-{program}`. Without it your calls show
  as `unknown` in the customer's API Usage Log, and Vaults with Client ID Filtering enabled
  will reject you outright.
