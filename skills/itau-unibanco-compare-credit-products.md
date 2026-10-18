---
name: itau-unibanco-compare-credit-products
description: Compare Itaú personal and business credit products (loans, financings,
  credit cards, overdraft, invoice financing) using Open Finance Brasil open data.
api: Itaú Unibanco Open Finance Brasil open data
operations:
- getPersonalLoans
- getBusinessLoans
- getPersonalFinancings
- getBusinessFinancings
- getPersonalCreditCards
- getBusinessCreditCards
- getPersonalUnarrangedAccountOverdraft
- getBusinessUnarrangedAccountOverdraft
- getBusinessInvoiceFinancings
---

# Compare Itaú personal and business credit products (loans, financings, credit cards, overdraft, invoice financing) using Open Finance Brasil open data.

## Steps

0. Optionally call `getStatus` (common API) to confirm the target API is operating.
1. `getPersonalLoans` — GET https://api.itau/open-banking/opendata-loans/v1/personal-loans: Obtém dados sobre empréstimos pessoa natural
2. `getBusinessLoans` — GET https://api.itau/open-banking/opendata-loans/v1/business-loans: Obtém dados sobre empréstimos pessoa jurídica
3. `getPersonalFinancings` — GET https://api.itau/open-banking/opendata-financings/v1/personal-financings: Obtém a lista de Financiamentos de Pessoa Natural.
4. `getBusinessFinancings` — GET https://api.itau/open-banking/opendata-financings/v1/business-financings: Obtém a lista de Financiamentos de Pessoa Jurídica.
5. `getPersonalCreditCards` — GET https://api.itau/open-banking/opendata-creditcards/v1/personal-credit-cards: Obtém dados sobre cartões de crédito pessoa natural
6. `getBusinessCreditCards` — GET https://api.itau/open-banking/opendata-creditcards/v1/business-credit-cards: Obtém dados sobre cartões de crédito pessoa jurídica
7. `getPersonalUnarrangedAccountOverdraft` — GET https://api.itau/open-banking/opendata-unarranged/v1/personal-unarranged-account-overdraft: Obtém a lista de adiantamento de depositante de Pessoa Natural.
8. `getBusinessUnarrangedAccountOverdraft` — GET https://api.itau/open-banking/opendata-unarranged/v1/business-unarranged-account-overdraft: Obtém a lista de adiantamento de depositante de Pessoa Jurídica.
9. `getBusinessInvoiceFinancings` — GET https://api.itau/open-banking/opendata-invoicefinancings/v1/business-invoice-financings: Obtém a lista de Direitos Creditórios Descontados de Pessoa Jurídica.

## Rules

- All operations are read-only GETs; they are safe to retry (idempotent).
- Paginate with the `page` (starts at 1) and `page-size` query parameters; follow `links.next` in the response until absent.
- The specs define no applied security requirement for these open-data endpoints.
- Responses follow the Open Finance Brasil envelope (`data`, `links`, `meta`); errors return the standard `errors[]` body.
