# UpGrowth MCP server: business data for Algeria, Tunisia and Morocco

A hosted [Model Context Protocol](https://modelcontextprotocol.io) server by [UpGrowth](https://www.upgrowth.dz) (Algiers). It gives AI assistants the official public data on creating and running a company in North Africa, with the official source of every record.

- **Endpoint (streamable HTTP):** `https://www.upgrowth.dz/mcp`
- **REST API and documentation:** https://www.upgrowth.dz/api (OpenAPI: https://www.upgrowth.dz/api/v1/openapi.json)
- **Free tier:** no sign-up, 100 calls a day, credit UpGrowth with a link.
- **Paid plans** (professionals, teams, platforms, data licences): https://www.upgrowth.dz/api, by application.

## Connect

**Claude** (claude.ai or Claude Desktop): Settings, Connectors, Add custom connector, URL `https://www.upgrowth.dz/mcp`.

**ChatGPT:** add it as a custom connector (developer mode) with the same URL.

**Cursor, VS Code and other MCP clients:**

```json
{
  "mcpServers": {
    "upgrowth": { "url": "https://www.upgrowth.dz/mcp" }
  }
}
```

With a paid plan, add the header `Authorization: Bearer <your key>`.

## What it covers

| Country | Data |
|---|---|
| Algeria | CNRC activity codes (2,136, with free, regulated or blocked status), ANAE auto-entrepreneur activities, wilayas, Journal officiel index 1962 to 2026 with search in the issue summaries, customs tariff sections and chapters, legal forms with official fees, CASNOS and IFU 2026 calculators, tax rates, social contributions, institutions |
| Tunisia | 24 governorates, legal forms with the RNE steps and fees, tax rates 2026, CNSS contributions and payroll levies, institutions |
| Morocco | 12 regions, legal forms with the CRI steps and fees, tax rates 2026, CNSS and AMO contributions, institutions, Bulletin officiel index 1912 to 2026 (French edition) |

More countries are added over time; `list_countries` always gives the current list.

## Tools

| Tool | What it answers |
|---|---|
| `list_countries` | Countries covered, with their datasets |
| `search_activity_codes`, `get_activity_code` | Algerian CNRC activity codes |
| `search_anae_activities`, `get_anae_activity` | Algerian auto-entrepreneur activities |
| `list_wilayas`, `get_wilaya` | Algerian wilayas, Tunisian governorates, Moroccan regions (`country`) |
| `list_jo_years`, `list_jo_issues`, `get_jo_issue` | Official gazette indexes: Algeria (JORA), Morocco (Bulletin officiel) |
| `search_jo_titles` | Titles of the texts in the Algerian Journal officiel summaries |
| `customs_tariff_sections`, `customs_tariff_chapters` | Algerian customs tariff |
| `creation_legal_forms` | Legal forms, partners, minimum capital, steps and official fees (`country`) |
| `calculate_casnos`, `calculate_ifu` | Algerian 2026 social contribution and flat tax estimates |
| `get_tax_rates` | Corporate tax, VAT, withholding and income tax rates (`country`) |
| `get_social_contributions` | Social contributions and payroll levies (`country`) |
| `list_institutions` | Registries, investment agencies, tax and social bodies (`country`) |

Every tool takes an optional `country` (ISO code, default `DZ`).

## Sources and accuracy

Each record carries the official page it was read from and the date. UpGrowth is a private company, not an official source; the calculators give estimates, not tax advice. Report an error: contact@upgrowth.dz.

## Terms

Free use by AI assistants and individuals with the credit line returned in `meta.attribution`: "Data from UpGrowth (https://www.upgrowth.dz)". Redistribution or bulk use needs a data licence: https://www.upgrowth.dz/api.

## Contact

contact@upgrowth.dz, https://www.upgrowth.dz/contact
