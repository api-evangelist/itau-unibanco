---
name: itau-unibanco-find-service-channels
description: Find Itaú branches, banking agents, electronic and phone service channels
  via Open Finance Brasil open data.
api: Itaú Unibanco Open Finance Brasil open data
operations:
- getBranches
- getBankingAgents
- getElectronicChannels
- getPhoneChannels
---

# Find Itaú branches, banking agents, electronic and phone service channels via Open Finance Brasil open data.

## Steps

0. Optionally call `getStatus` (common API) to confirm the target API is operating.
1. `getBranches` — GET https://api.itau/open-banking/channels/v2/branches: Obtém a lista de dependências próprias da instituição financeira.
2. `getBankingAgents` — GET https://api.itau/open-banking/channels/v2/banking-agents: Obtém a lista de correspondentes bancários da instituição financeira.
3. `getElectronicChannels` — GET https://api.itau/open-banking/channels/v2/electronic-channels: Obtém a lista de canais eletrônicos de atendimento da instituição financeira.
4. `getPhoneChannels` — GET https://api.itau/open-banking/channels/v2/phone-channels: Obtém a lista de canais telefônicos de atendimento da instituição financeira.

## Rules

- All operations are read-only GETs; they are safe to retry (idempotent).
- Paginate with the `page` (starts at 1) and `page-size` query parameters; follow `links.next` in the response until absent.
- The specs define no applied security requirement for these open-data endpoints.
- Responses follow the Open Finance Brasil envelope (`data`, `links`, `meta`); errors return the standard `errors[]` body.
