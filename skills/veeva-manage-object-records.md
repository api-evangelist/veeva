---
name: veeva-manage-object-records
description: CRUD Veeva Vault object records against a tenant-configured data model, discovering object metadata before writing.
api: veeva:veeva-objects-api
generated: '2026-08-15'
method: generated
operations:
  - listObjectRecords
  - createObjectRecord
  - getObjectRecord
  - updateObjectRecord
  - deleteObjectRecord
  - executeVQLQuery
---

# Create and maintain Vault object records

## Before you start

- Vault objects are **configurable**. `{objectName}` is the object's API name, and the suffix
  tells you where it came from: `__v` Veeva-standard, `__sys` Veeva-system, `__c`
  customer-configured. Never hard-code a `__c` object across tenants.
- Field sets, picklist values, and relationships differ per Vault. Discover, then write.

## Steps

1. **Discover.** Retrieve Object Metadata for `{objectName}`, then Retrieve Object Field
   Metadata for any field you intend to set. This is what makes an integration portable
   between two customers' Vaults.

2. **List / find.** Call `listObjectRecords` — `GET /vobjects/{objectName}` — for a straight
   listing, or `executeVQLQuery` when you need filtering, relationship traversal, or joins.
   VQL is almost always the cheaper call.

3. **Create.** Call `createObjectRecord` — `POST /vobjects/{objectName}`. For more than a
   handful, use the bulk create/upsert endpoint (500 records per request) instead of looping.

4. **Read.** Call `getObjectRecord` — `GET /vobjects/{objectName}/{recordId}`.

5. **Update.** Call `updateObjectRecord` — `PUT /vobjects/{objectName}/{recordId}`.

6. **Delete.** Call `deleteObjectRecord` — `DELETE /vobjects/{objectName}/{recordId}`.
   Cascade delete and deep copy are asynchronous **jobs**, not synchronous deletes.

## Rules

- **Poll jobs no more than once per 10 seconds per `job_id`.** The Job Status endpoint is
  rate limited independently and returns `API_LIMIT_EXCEEDED` if you exceed it. This limit is
  per job, and the burst headers do not describe it.
- **No idempotency key.** For creates, prefer the **upsert** form with a natural key over
  create-then-retry. That is the only replay-safe write Vault offers.
- **`OPERATION_NOT_ALLOWED`** means a configured business rule blocked the write — a lifecycle
  state, an entry criterion, a validation rule. It is not transient; retrying will not help.
- **`RACE_CONDITION`** means a concurrent update to the same record. Re-read, then re-apply.
- Relationships and the platform entity graph: `data-model/veeva-data-model.yml`.
