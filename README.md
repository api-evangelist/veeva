# Veeva (veeva)
Veeva Systems is a leader in cloud-based software for the global life sciences industry, providing solutions to help pharmaceutical and biotechnology companies bring products to market more efficiently.

**URL:** [https://developer.veevavault.com/](https://developer.veevavault.com/)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Clinical, Life Sciences, Pharma, QMS, Regulatory

## Timestamps

- **Created:** 2026-03-18
- **Modified:** 2026-05-03

## APIs

### Veeva Vault Platform API
Veeva Vault provides life sciences cloud platform APIs for regulatory document management, quality management (QMS), clinical operations, and commercial content management. REST APIs enable document lifecycle management, workflow automation, and compliance-validated data exchange.

**Human URL:** [https://developer.veevavault.com/](https://developer.veevavault.com/)

#### Tags:

 - Clinical, Life Sciences, Pharma, QMS, Regulatory

#### Properties

- [Portal](https://developer.veevavault.com/)
- [Documentation](https://developer.veevavault.com/docs)
- [Reference](https://developer.veevavault.com/api/25.3/)
- [Authentication](https://developer.veevavault.com/api/25.3/)
- [ChangeLog](https://developer.veevavault.com/rn/25.3/)
- [GettingStarted](https://developer.veevavault.com/docs)
- [OpenAPI](openapi/veeva-vault-openapi.yml)
- [JSONSchema - Auth Response Schema](json-schema/veeva-vault-auth-response-schema.json)
- [JSONSchema - Document Fields Schema](json-schema/veeva-vault-document-fields-schema.json)
- [JSONSchema - Document List Response Schema](json-schema/veeva-vault-document-list-response-schema.json)
- [JSONSchema - Document Create Response Schema](json-schema/veeva-vault-document-create-response-schema.json)
- [JSONSchema - Object List Response Schema](json-schema/veeva-vault-object-list-response-schema.json)
- [JSONSchema - Query Response Schema](json-schema/veeva-vault-query-response-schema.json)
- [JSONStructure - Auth Response Structure](json-structure/veeva-vault-auth-response-structure.json)
- [JSONStructure - Document Fields Structure](json-structure/veeva-vault-document-fields-structure.json)
- [Example - Auth Response Example](examples/veeva-vault-auth-response-example.json)
- [Example - Document Fields Example](examples/veeva-vault-document-fields-example.json)

### Veeva Vault Java SDK
The Veeva Vault Java SDK (VAPIL) is an open-source Java-based REST API client for the Vault REST API. Provides type-safe access to all Vault API operations including document management, object CRUD, workflow execution, and administrative functions.

**Human URL:** [https://developer.veevavault.com/sdk/](https://developer.veevavault.com/sdk/)

#### Tags:

 - Java, Life Sciences, Pharma, SDK

#### Properties

- [Documentation](https://developer.veevavault.com/sdk/)
- [SDKs](https://github.com/veeva/vault-api-library)
- [SDKs - Maven Central](https://mvnrepository.com/artifact/com.veeva/vault-api-library)

### Veeva Vault Query Language (VQL) API
Vault Query Language (VQL) provides SQL-like query capabilities for accessing and retrieving Vault data. Supports SELECT, FROM, WHERE, ORDER BY, relationship queries, and functions for querying documents, objects, users, workflows, and system data.

**Human URL:** [https://developer.veevavault.com/vql/](https://developer.veevavault.com/vql/)

#### Tags:

 - Life Sciences, Pharma, Query Language, SQL

#### Properties

- [Documentation](https://developer.veevavault.com/vql/)
- [OpenAPI](openapi/veeva-vault-openapi.yml)

### Veeva Vault Direct Data API
The Veeva Vault Direct Data API provides high-speed, read-only bulk access to Vault data for integration, analytics, and reporting purposes. Supports bulk export of documents, objects, and attachment field files for up to 500 records.

**Human URL:** [https://developer.veevavault.com/docs](https://developer.veevavault.com/docs)

#### Tags:

 - Bulk Data, Data Access, Life Sciences, Pharma

#### Properties

- [Documentation](https://developer.veevavault.com/docs)

## Common Properties

- [Website](https://www.veeva.com/)
- [Portal](https://developer.veevavault.com/)
- [Documentation](https://developer.veevavault.com/docs)
- [GettingStarted](https://developer.veevavault.com/docs)
- [Authentication](https://developer.veevavault.com/api/25.3/)
- [ChangeLog](https://developer.veevavault.com/rn/25.3/)
- [SDKs](https://developer.veevavault.com/sdk/)
- [Support](https://support.veeva.com/hc/en-us)
- [PrivacyPolicy](https://www.veeva.com/privacy/)
- [GitHubOrganization](https://github.com/veeva)
- [JSONSchema - Vault Document Schema](json-schema/veeva-vault-document-schema.json)
- [JSONLDContext](json-ld/veeva-context.jsonld)
- [SpectralRules - Veeva Vault API Spectral Rules](rules/veeva-spectral-rules.yml)
- [Vocabulary - Veeva Vocabulary](vocabulary/veeva-vocabulary.yml)
- [NaftikoCapability - Vault Document Management](capabilities/vault-document-management.yaml)

## Features

| Name | Description |
|------|-------------|
| Document Lifecycle Management | Full lifecycle management for controlled documents including draft, review, approval, and archival states with audit trails for regulatory compliance. |
| Vault Query Language | SQL-like query engine for retrieving Vault data across documents, objects, users, and workflows with support for relationship traversal. |
| Direct Data API | High-speed bulk data export for up to 500 records at a time for analytics, reporting, and integration with downstream systems. |
| Vault Object CRUD | Create, read, update, and delete operations on configurable Vault business objects (studies, products, sites, etc.) via REST API. |
| Session Authentication | Username/password authentication returning a session ID for subsequent API calls, with multi-vault support for complex enterprise deployments. |
| Java SDK (VAPIL) | Open-source Java client library providing type-safe access to all Vault REST API operations with automatic session management and error handling. |

## Use Cases

| Name | Description |
|------|-------------|
| Regulatory Document Submission | Automate the assembly and submission of regulatory dossiers (CTD, eCTD) by programmatically managing document lifecycle, approvals, and publishing. |
| Clinical Trial Data Management | Integrate Vault with CTMS, EDC, and LIMS systems to automate study document workflows, protocol amendments, and site activation packages. |
| Quality Management Automation | Automate SOPs, CAPAs, deviations, and audit workflows in QMS Vault through lifecycle actions, object creation, and workflow task assignment. |
| Content Analytics | Export Vault document and object data in bulk for BI dashboards, compliance reporting, and cross-Vault analytics using the Direct Data API. |
| Enterprise Integration | Integrate Vault with SAP, Salesforce, Veeva CRM, and other enterprise systems using REST APIs for bidirectional data synchronization. |

## Integrations

| Name | Description |
|------|-------------|
| Veeva CRM | Bidirectional integration between Vault and Veeva CRM for commercial content lifecycle management and promotional material approval workflows. |
| Salesforce | Connect Vault document approval workflows with Salesforce opportunities, accounts, and contacts via REST API integration. |
| SAP | Synchronize quality events, deviations, and regulatory submissions between Vault and SAP ERP using REST API and Direct Data API. |
| MuleSoft | Pre-built MuleSoft connectors for Vault REST API integration with enterprise middleware platforms and iPaaS solutions. |
| Microsoft Azure | Deploy Vault integrations on Azure using Logic Apps, Azure Functions, or Azure Data Factory with Vault REST API support. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Veeva Vault REST API](openapi/veeva-vault-openapi.yml)

### JSON Schema

- [veeva-vault-auth-response-schema.json](json-schema/veeva-vault-auth-response-schema.json)
- [veeva-vault-document-create-response-schema.json](json-schema/veeva-vault-document-create-response-schema.json)
- [veeva-vault-document-fields-schema.json](json-schema/veeva-vault-document-fields-schema.json)
- [veeva-vault-document-list-response-schema.json](json-schema/veeva-vault-document-list-response-schema.json)
- [veeva-vault-document-response-schema.json](json-schema/veeva-vault-document-response-schema.json)
- [veeva-vault-document-schema.json](json-schema/veeva-vault-document-schema.json)
- [veeva-vault-document-update-response-schema.json](json-schema/veeva-vault-document-update-response-schema.json)
- [veeva-vault-object-create-response-schema.json](json-schema/veeva-vault-object-create-response-schema.json)
- [veeva-vault-object-list-response-schema.json](json-schema/veeva-vault-object-list-response-schema.json)
- [veeva-vault-object-record-response-schema.json](json-schema/veeva-vault-object-record-response-schema.json)
- [veeva-vault-query-response-schema.json](json-schema/veeva-vault-query-response-schema.json)
- [veeva-vault-user-list-response-schema.json](json-schema/veeva-vault-user-list-response-schema.json)

### JSON Structure

- [veeva-vault-auth-response-structure.json](json-structure/veeva-vault-auth-response-structure.json)
- [veeva-vault-document-create-response-structure.json](json-structure/veeva-vault-document-create-response-structure.json)
- [veeva-vault-document-fields-structure.json](json-structure/veeva-vault-document-fields-structure.json)
- [veeva-vault-document-list-response-structure.json](json-structure/veeva-vault-document-list-response-structure.json)
- [veeva-vault-document-response-structure.json](json-structure/veeva-vault-document-response-structure.json)
- [veeva-vault-document-structure.json](json-structure/veeva-vault-document-structure.json)
- [veeva-vault-document-update-response-structure.json](json-structure/veeva-vault-document-update-response-structure.json)
- [veeva-vault-object-create-response-structure.json](json-structure/veeva-vault-object-create-response-structure.json)
- [veeva-vault-object-list-response-structure.json](json-structure/veeva-vault-object-list-response-structure.json)
- [veeva-vault-object-record-response-structure.json](json-structure/veeva-vault-object-record-response-structure.json)
- [veeva-vault-query-response-structure.json](json-structure/veeva-vault-query-response-structure.json)
- [veeva-vault-user-list-response-structure.json](json-structure/veeva-vault-user-list-response-structure.json)

### JSON-LD

- [veeva-context.jsonld](json-ld/veeva-context.jsonld)

### Examples

- [veeva-vault-auth-response-example.json](examples/veeva-vault-auth-response-example.json)
- [veeva-vault-document-create-response-example.json](examples/veeva-vault-document-create-response-example.json)
- [veeva-vault-document-fields-example.json](examples/veeva-vault-document-fields-example.json)
- [veeva-vault-document-list-response-example.json](examples/veeva-vault-document-list-response-example.json)
- [veeva-vault-document-response-example.json](examples/veeva-vault-document-response-example.json)
- [veeva-vault-document-example.json](examples/veeva-vault-document-example.json)
- [veeva-vault-document-update-response-example.json](examples/veeva-vault-document-update-response-example.json)
- [veeva-vault-object-create-response-example.json](examples/veeva-vault-object-create-response-example.json)
- [veeva-vault-object-list-response-example.json](examples/veeva-vault-object-list-response-example.json)
- [veeva-vault-object-record-response-example.json](examples/veeva-vault-object-record-response-example.json)
- [veeva-vault-query-response-example.json](examples/veeva-vault-query-response-example.json)
- [veeva-vault-user-list-response-example.json](examples/veeva-vault-user-list-response-example.json)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Veeva Vault REST API](capabilities/shared/vault-api.yaml) — 15 operations for document lifecycle, object CRUD, VQL queries, and user management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Vault Document Management](capabilities/vault-document-management.yaml) | vault-api | 13 | Regulatory Affairs Specialist, QMS Coordinator, Clinical Operations Manager |

## Vocabulary

- [Veeva Vocabulary](vocabulary/veeva-vocabulary.yml) — Unified taxonomy mapping 5 resources, 9 actions, 1 workflow, and 3 personas across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Veeva Vault API Spectral Rules](rules/veeva-spectral-rules.yml) — 32 rules across 13 categories enforcing Veeva Vault API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
