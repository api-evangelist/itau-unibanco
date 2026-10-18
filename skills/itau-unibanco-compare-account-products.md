---
name: itau-unibanco-compare-account-products
description: Retrieve Itaú personal and business account product data (fees, service
  bundles) via Open Finance Brasil open data.
api: Itaú Unibanco Open Finance Brasil open data
operations:
- getPersonalAccounts
- getBusinessAccounts
---

# Retrieve Itaú personal and business account product data (fees, service bundles) via Open Finance Brasil open data.

## Steps

0. Optionally call `getStatus` (common API) to confirm the target API is operating.
1. `getPersonalAccounts` — GET https://api.itau/open-banking/opendata-accounts/v1/personal-accounts: Obtém dados das contas pessoa natural
2. `getBusinessAccounts` — GET https://api.itau/open-banking/opendata-accounts/v1/business-accounts: Obtém dados das contas pessoa jurídica

## Rules

- All operations are read-only GETs; they are safe to retry (idempotent).
- Paginate with the `page` (starts at 1) and `page-size` query parameters; follow `links.next` in the response until absent.
- The specs define no applied security requirement for these open-data endpoints.
- Responses follow the Open Finance Brasil envelope (`data`, `links`, `meta`); errors return the standard `errors[]` body.
