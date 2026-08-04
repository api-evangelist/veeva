# veeva (veeva)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Veeva Systems is a leader in cloud-based software for the global life sciences industry, providing solutions to help pharmaceutical and biotechnology companies bring products to market more efficiently.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/veeva/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/veeva/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-05-19

## APIs

### Veeva Vault Platform API

Veeva Vault provides life sciences cloud platform APIs for regulatory document management, quality management (QMS), clinical operations, and commercial content management. REST APIs enable document lifecycle management, workflow automation, and compliance-validated data exchange.

- **Human URL:** [https://developer.veevavault.com/](https://developer.veevavault.com/)
- **Base URL:** `https://myvault.veevavault.com/api/v25.3`

#### Tags

- Clinical
- Life Sciences
- Pharma
- QMS
- Regulatory

#### Properties

- [Portal](https://developer.veevavault.com/)
- [Documentation](https://developer.veevavault.com/docs)
- [Reference](https://developer.veevavault.com/api/25.3/)
- [Authentication](https://developer.veevavault.com/api/25.3/)
- [Changelog](https://developer.veevavault.com/rn/25.3/)
- [Getting Started](https://developer.veevavault.com/docs)
- [OpenAPI](openapi/veeva-vault-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/veeva-vault.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/veeva-vault.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/veeva-vault-auth-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-document-fields-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-document-list-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-document-create-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-document-update-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-document-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-object-list-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-object-create-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-object-record-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-query-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/veeva-vault-user-list-response-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/veeva-vault-auth-response-structure.json)
- [JSON Structure](json-structure/veeva-vault-document-fields-structure.json)
- [JSON Structure](json-structure/veeva-vault-document-list-response-structure.json)
- [JSON Structure](json-structure/veeva-vault-query-response-structure.json)
- [Example](examples/veeva-vault-auth-response-example.json)
- [Example](examples/veeva-vault-document-fields-example.json)
- [Example](examples/veeva-vault-document-list-response-example.json)
- [Example](examples/veeva-vault-query-response-example.json)

### Veeva Vault Java SDK

The Veeva Vault Java SDK (VAPIL) is an open-source Java-based REST API client for the Vault REST API. Provides type-safe access to all Vault API operations including document management, object CRUD, workflow execution, and administrative functions.

- **Human URL:** [https://developer.veevavault.com/sdk/](https://developer.veevavault.com/sdk/)
- **Base URL:** `https://myvault.veevavault.com/api`

#### Tags

- Java
- Life Sciences
- Pharma
- SDK

#### Properties

- [Documentation](https://developer.veevavault.com/sdk/)
- [S D Ks](https://github.com/veeva/vault-api-library)
- [S D Ks](https://mvnrepository.com/artifact/com.veeva/vault-api-library)
- [Postman Collection](collections/veeva-vault.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/veeva-vault.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Veeva Vault Query Language (VQL) API

Vault Query Language (VQL) provides SQL-like query capabilities for accessing and retrieving Vault data. Supports SELECT, FROM, WHERE, ORDER BY, relationship queries, and functions for querying documents, objects, users, workflows, and system data.

- **Human URL:** [https://developer.veevavault.com/vql/](https://developer.veevavault.com/vql/)
- **Base URL:** `https://myvault.veevavault.com/api`

#### Tags

- Life Sciences
- Pharma
- Query Language
- SQL

#### Properties

- [Documentation](https://developer.veevavault.com/vql/)
- [OpenAPI](openapi/veeva-vault-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/veeva-vault.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/veeva-vault.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Veeva Vault Direct Data API

The Veeva Vault Direct Data API provides high-speed, read-only bulk access to Vault data for integration, analytics, and reporting purposes. Supports bulk export of documents, objects, and attachment field files for up to 500 records.

- **Human URL:** [https://developer.veevavault.com/docs](https://developer.veevavault.com/docs)
- **Base URL:** `https://myvault.veevavault.com/api`

#### Tags

- Bulk Data
- Data Access
- Life Sciences
- Pharma

#### Properties

- [Documentation](https://developer.veevavault.com/docs)
- [Postman Collection](collections/veeva-vault.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/veeva-vault.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/veeva-systems)
- [Website](https://www.veeva.com/)
- [Portal](https://developer.veevavault.com/)
- [Documentation](https://developer.veevavault.com/docs)
- [Getting Started](https://developer.veevavault.com/docs)
- [Authentication](https://developer.veevavault.com/api/25.3/)
- [Changelog](https://developer.veevavault.com/rn/25.3/)
- [S D Ks](https://developer.veevavault.com/sdk/)
- [Support](https://support.veeva.com/hc/en-us)
- [Privacy Policy](https://www.veeva.com/privacy/)
- [GitHub Organization](https://github.com/veeva)
- [JSON Schema](json-schema/veeva-vault-document-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N L D Context](json-ld/veeva-context.jsonld)
- [Spectral Rules](rules/veeva-spectral-rules.yml)
- [Vocabulary](vocabulary/veeva-vocabulary.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Integrations](https://www.veeva.com/meet-veeva/partners/)

## Maintainers

**Email:** kin@apievangelist.com
