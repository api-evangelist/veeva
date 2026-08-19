---
name: veeva-manage-document-lifecycle
description: Create, read, update, download and delete controlled documents in a Veeva Vault, respecting version IDs, bulk caps and the 4 GB file limit.
api: veeva:veeva-documents-api
generated: '2026-08-15'
method: generated
operations:
  - listDocuments
  - createDocument
  - getDocument
  - updateDocument
  - deleteDocument
  - downloadDocumentFile
---

# Manage a Vault document through its lifecycle

## Before you start

- Authenticate first — see `veeva-authenticate-and-query`.
- Document IDs come in two forms: bare (`1001`) and versioned (`1001_1_3`, i.e.
  `id_major_minor`). A bare ID resolves to the **latest** version. If you need a specific
  version, pass the versioned form explicitly — this is the single most common source of
  "wrong content" bugs against Vault.
- A Vault's document fields are **configured per tenant**. Do not assume a field exists.

## Steps

1. **Discover the field set.** Retrieve Document Fields before writing anything, so you send
   the fields this Vault actually has. Sending an unknown attribute returns
   `ATTRIBUTE_NOT_SUPPORTED`.

2. **List.** Call `listDocuments` — `GET /objects/documents`. Passing a filter that does not
   exist returns `INVALID_FILTER`, not an empty result.

3. **Create.** Call `createDocument` — `POST /objects/documents`. Uploaded files are capped at
   4 GB; exceeding it returns `EXCEEDS_FILE_MAX_SIZE`. For volume, use the bulk create endpoint
   rather than looping this one — a single bulk call handles up to 500 records and is the
   documented way to stay inside the burst limit.

4. **Read.** Call `getDocument` — `GET /objects/documents/{documentId}`. Call
   `downloadDocumentFile` — `GET /objects/documents/{documentId}/file` — for the binary.

5. **Update.** Call `updateDocument` — `PUT /objects/documents/{documentId}`. Update only what
   changed; re-sending unchanged fields spends burst budget for nothing.

6. **Delete.** Call `deleteDocument` — `DELETE /objects/documents/{documentId}`.

## Rules

- **No idempotency key exists.** A timed-out create may or may not have created a document.
  Before retrying, query for it — do not fire the same `createDocument` twice.
- **`INSUFFICIENT_ACCESS` is ambiguous on `/actions` endpoints.** Vault returns it both for a
  genuine permission failure and for a resource that does not exist. Do not report it to a user
  as "access denied" without checking existence.
- **`OPERATION_IN_PROGRESS`** means another operation already holds that document. Back off and
  poll; do not parallelise writes to the same document.
- **Respect the throttle.** When `X-VaultAPI-ResponseDelay` appears, Vault is already delaying
  you. Slow down rather than adding concurrency.
- Full error vocabulary: `errors/veeva-problem-types.yml`.
