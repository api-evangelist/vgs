# Very Good Security (vgs)

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
