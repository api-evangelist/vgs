# Very Good Security (vgs)

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

Very Good Security (VGS) is a data security and tokenization platform that lets companies collect, protect, and exchange sensitive data (cards, PII, bank accounts, credentials) without it touching their own systems, reducing PCI DSS and compliance scope. The platform exposes a Vault HTTP API for tokenization (aliases / redact / reveal), an Accounts management API for vaults, routes, and organizations, and a forward/reverse Proxy that aliases and de-aliases data in transit.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vgs/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vgs/refs/heads/main/apis.yml)

## Tags

- Security
- Tokenization
- Data Privacy
- PCI Compliance
- Vault

## Timestamps

- **Created:** 2026-06-20
- **Modified:** 2026-06-20

## APIs

### VGS Vault Tokenization API

The VGS Vault HTTP API stores, retrieves, and manages sensitive values as aliases (tokens). Create aliases by value or by reference, reveal single or multiple aliases, update data classifiers, and delete aliases. Supports many alias formats (UUID, FPE_SIX_T_FOUR, NUM_LENGTH_PRESERVING, and more) and PERSISTENT or VOLATILE storage. Authenticated with HTTP Basic access credentials.

- **Human URL:** [https://www.verygoodsecurity.com/docs/vault/api/](https://www.verygoodsecurity.com/docs/vault/api/)
- **Base URL:** `https://api.sandbox.verygoodvault.com`

#### Tags

- Tokenization
- Aliases
- Vault

#### Properties

- [Documentation](https://docs.verygoodsecurity.com/vault/tokens)
- [API Reference](https://www.verygoodsecurity.com/docs/vault/api/)
- [OpenAPI](openapi/vgs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vgs.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vgs.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### VGS Accounts Management API

The VGS Accounts / control plane API administers organizations and vaults, reads account and access-log details, and manages the resources behind the platform. Authenticated with a Bearer access token obtained from the VGS OAuth2 client-credentials endpoint, with service-account scopes such as vaults:read, vaults:write, organizations:read, and access-logs:read.

- **Human URL:** [https://docs.verygoodsecurity.com/vault/platform/iam](https://docs.verygoodsecurity.com/vault/platform/iam)
- **Base URL:** `https://accounts.apps.verygoodsecurity.com`

#### Tags

- Management
- Vaults
- Organizations

#### Properties

- [Documentation](https://docs.verygoodsecurity.com/vault/developer-tools/vgs-cli/service-account)
- [API Reference](https://docs.verygoodsecurity.com/vault/platform/iam)
- [OpenAPI](openapi/vgs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vgs.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vgs.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### VGS Routes & Proxy API

Manage inbound (reverse) and outbound (forward) proxy routes that redact and reveal sensitive data in transit. Routes are CRUD-managed through the Accounts API and applied to a vault; the data plane is reached over the proxy hosts (for example {vault-id}.sandbox.verygoodproxy.com for inbound and the forward proxy on port 8443 for outbound) using HTTP Basic credentials.

- **Human URL:** [https://docs.verygoodsecurity.com/vault/http-proxy/outbound-connection](https://docs.verygoodsecurity.com/vault/http-proxy/outbound-connection)
- **Base URL:** `https://accounts.apps.verygoodsecurity.com`

#### Tags

- Proxy
- Routes
- Inbound Outbound

#### Properties

- [Documentation](https://docs.verygoodsecurity.com/vault/http-proxy/inbound-connection)
- [API Reference](https://docs.verygoodsecurity.com/vault/http-proxy/outbound-connection)
- [OpenAPI](openapi/vgs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### VGS Functions API

VGS Compute Functions run custom code inside the VGS security boundary to transform sensitive payloads (for example reformatting, enrichment, or custom tokenization) as part of a route, managed through the Accounts API and bound to a vault.

- **Human URL:** [https://docs.verygoodsecurity.com/vault/vgs-compute/functions](https://docs.verygoodsecurity.com/vault/vgs-compute/functions)
- **Base URL:** `https://accounts.apps.verygoodsecurity.com`

#### Tags

- Functions
- Compute
- Serverless

#### Properties

- [Documentation](https://docs.verygoodsecurity.com/vault/vgs-compute/functions)
- [OpenAPI](openapi/vgs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### VGS Organizations API

Read organization details, members, vault assignments, and tenant access logs through the VGS Accounts control plane, governed by service-account scopes (organizations:read, access-logs:read) and Bearer authentication.

- **Human URL:** [https://docs.verygoodsecurity.com/vault/platform/iam](https://docs.verygoodsecurity.com/vault/platform/iam)
- **Base URL:** `https://accounts.apps.verygoodsecurity.com`

#### Tags

- Organizations
- IAM
- Access Logs

#### Properties

- [Documentation](https://docs.verygoodsecurity.com/vault/platform/iam)
- [OpenAPI](openapi/vgs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [GitHub Organization](https://github.com/verygoodsecurity)
- [LinkedIn](https://www.linkedin.com/company/verygoodsecurity)
- [Website](https://www.verygoodsecurity.com)
- [Documentation](https://docs.verygoodsecurity.com)
- [Plans](plans/vgs-plans-pricing.yml)
- [Rate Limits](rate-limits/vgs-rate-limits.yml)
- [Fin Ops](finops/vgs-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
