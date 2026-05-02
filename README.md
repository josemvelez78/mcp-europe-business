# MCP Europe Business Suite

[![Glama badge](https://glama.ai/mcp/servers/josemvelez78/mcp-europe-business/badges/score.svg)](https://glama.ai/mcp/servers/josemvelez78/mcp-europe-business)

European business compliance suite for AI agents — 28 tools covering tax ID validation, invoice rules, VAT calculations, e-invoicing obligations, payment terms, labor calendar helpers and postal code validation for PT, ES, FR, DE, IT, UK, NL and 18+ European countries.

## Quickstart

**Option 1 — MCPize (hosted, no setup):**

https://mcpize.com/mcp/mcp-europe-business-suite

Free tier: 500 requests/month, no credit card required. [Get your API key →](https://mcpize.com)

**Option 2 — Claude Desktop (direct endpoint):**

{
  "mcpServers": {
    "mcp-europe-business": {
      "url": "https://mcp-europe-business-production.up.railway.app/mcp"
    }
  }
}

## What it does

28 tools in 4 modules for European business compliance workflows. No auth required. Read-only and idempotent.

**Typical use cases:**
- Validate tax IDs for EU customers (NIF, NIE, CIF, SIRET, TVA, Codice Fiscale, Partita IVA, USt-IdNr, UK VAT, KVK)
- Verify IBANs before processing SEPA transfers
- Calculate VAT breakdowns for invoices and e-commerce checkouts
- Validate invoice schemas before submission
- Determine VAT treatment for cross-border EU transactions (reverse charge, OSS, IOSS)
- Look up e-invoicing obligations by country (IT mandatory since 2019, DE from 2025, FR from 2026)
- Get payment terms and invoice requirements per country
- Calculate working days and next payment dates across EU countries

## Tools

### Module 1 — Validation (17 tools)

| Tool | Description |
|------|-------------|
| `validate_nif` | Portuguese NIF — modulo-11 checksum |
| `validate_nif_es` | Spanish NIF, NIE and CIF |
| `validate_siret` | French SIRET — Luhn algorithm |
| `validate_tva_fr` | French TVA intracom VAT number |
| `validate_codice_fiscale` | Italian Codice Fiscale (individuals) |
| `validate_partita_iva` | Italian Partita IVA (companies) |
| `validate_vat_de` | German USt-IdNr — MOD-11-10 |
| `validate_vat_uk` | UK VAT number — HMRC MOD-97 |
| `validate_kvk_nl` | Dutch KVK chamber of commerce number |
| `validate_iban` | IBAN — ISO 13616 MOD-97, 18 EU countries |
| `validate_postal_code` | Postal codes for PT, ES, FR, DE, IT, NL, BE, PL, SE, AT, IE, GR, HU, RO, UK |
| `get_vat_rate` | VAT rates for 18 EU member states |
| `get_portugal_holidays` | Portuguese national public holidays |
| `get_spain_holidays` | Spanish national public holidays |
| `get_france_holidays` | French national public holidays (Easter-dynamic) |
| `calculate_working_days` | Working days between two dates (Portugal) |
| `format_number_european` | Number formatting by European locale |

### Module 2 — Business Rules (4 tools)

| Tool | Description |
|------|-------------|
| `get_payment_terms` | Legal B2B payment terms by country (EU Directive 2011/7/EU) |
| `get_invoice_requirements` | Mandatory invoice fields by country |
| `get_vat_exemption_threshold` | Small business VAT exemption thresholds |
| `get_einvoicing_rules` | E-invoicing obligations — B2G/B2B/B2C by country |

### Module 3 — Labor Helpers (3 tools)

| Tool | Description |
|------|-------------|
| `get_public_holidays_range` | Holidays in a date range for PT, ES, FR, DE, IT, NL, BE, UK |
| `calculate_working_days_eu` | Working days between two dates for any EU country |
| `get_next_payment_date` | Next valid payment date by rule (last/first working day, nth working day) |

### Module 4 — Invoice & VAT (4 tools)

| Tool | Description |
|------|-------------|
| `validate_invoice_schema` | Validates invoice JSON against mandatory fields per country |
| `calculate_vat_breakdown` | VAT breakdown by rate for invoice line items |
| `suggest_vat_treatment` | Suggests VAT treatment for cross-border EU transactions |
| `calculate_vat_amount` | Calculates net/VAT/gross from net or gross amount |

## Supported Countries

Portugal, Spain, France, Germany, Italy, United Kingdom, Netherlands, Belgium, Poland, Sweden, Denmark, Finland, Austria, Ireland, Greece, Hungary, Romania, Czech Republic, Croatia.

## Pricing

| Plan | Requests | Price |
|------|----------|-------|
| Free | 500/month | $0 — no credit card |
| Pro | 10,000/month | $19/month or $182/year |
| Overage | Beyond plan | $0.001/request |

Available via [MCPize](https://mcpize.com/mcp/mcp-europe-business-suite).

> **Disclaimer:** Business rules, payment terms, invoice requirements and e-invoicing information are provided as reference only — not legal or tax advice. Always verify with a qualified professional.

## License

MIT
