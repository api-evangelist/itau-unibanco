---
name: itau-unibanco-check-api-status
description: Check implementation status and scheduled outages of Itaú Open Finance
  Brasil APIs before calling them.
api: Itaú Unibanco Open Finance Brasil open data
operations:
- getStatus
- getOutage
---

# Check implementation status and scheduled outages of Itaú Open Finance Brasil APIs before calling them.

## Steps

1. `getStatus` — GET https://api.itau/open-banking/discovery/v2/status: Descrição do status da implementação das APIs do OFB
2. `getOutage` — GET https://api.itau/open-banking/discovery/v2/outages: a descrição referente ao código de status retornado pelas APIs

## Rules

- All operations are read-only GETs; they are safe to retry (idempotent).
- Paginate with the `page` (starts at 1) and `page-size` query parameters; follow `links.next` in the response until absent.
- The specs define no applied security requirement for these open-data endpoints.
- Responses follow the Open Finance Brasil envelope (`data`, `links`, `meta`); errors return the standard `errors[]` body.
