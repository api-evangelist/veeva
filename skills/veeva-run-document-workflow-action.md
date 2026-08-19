---
name: veeva-run-document-workflow-action
description: Move a Veeva Vault document through its lifecycle by invoking a configured user action, and handle the asynchronous and permission failures correctly.
api: veeva:veeva-workflows-api
generated: '2026-08-15'
method: generated
operations:
  - performDocumentAction
  - getDocument
  - executeVQLQuery
---

# Run a document lifecycle / workflow action

## Before you start

- Lifecycle actions are **configured per Vault**. The set of valid `{actionName}` values for a
  document depends on its type, its current lifecycle state, and the calling user's role. Never
  hard-code an action name without discovering it first.
- Authenticate first — see `veeva-authenticate-and-query`.

## Steps

1. **Find the document and its state.** Call `getDocument`, or `executeVQLQuery` to pull
   `id`, `status__v` and `lifecycle__v` for a set of documents in one call.

2. **Discover the available actions.** Retrieve Document User Actions for the document. This
   returns the actions this user can perform on this document in its current state — that is
   the list you drive from.

3. **Invoke.** Call `performDocumentAction` —
   `POST /objects/documents/{documentId}/actions/{actionName}`.

4. **Confirm the transition.** Re-read the document and verify its lifecycle state actually
   changed. Do not treat HTTP 200 as proof: check `responseStatus` in the body, and for
   workflow actions the state change may complete asynchronously.

## Rules

- **`INSUFFICIENT_ACCESS` on an `/actions` endpoint may mean the action does not exist**, not
  that the user lacks permission. Veeva documents this collision explicitly. Always
  re-discover the available user actions before reporting a permission problem.
- **`OPERATION_NOT_ALLOWED`** means entry criteria for the transition were not met. Surface the
  message to the user; do not retry.
- **`OPERATION_IN_PROGRESS`** means another action is already running on that document. Poll,
  do not parallelise.
- **Never blind-retry an action.** There is no idempotency key. An approval or a state
  transition fired twice is a compliance event in a GxP Vault, not a harmless duplicate.
- **Bulk workflow actions exist.** For many documents, use the Bulk Active Workflow Actions
  endpoints instead of looping this operation.
