# Brazil Case Law MCP (STJ, STF jurisprudência)

A hosted MCP server that searches official Brazilian case law (jurisprudência) from the Superior Tribunal de Justiça
(STJ) and the Supremo Tribunal Federal (STF): by legal terms, by party or lawyer, or by company CNPJ. One search returns
the newest matching decisions as compact JSON: citation, parties, ementa summary, tese and links to the official pages.

It runs on Apify: [apify.com/siteacs/brazil-case-law-mcp](https://apify.com/siteacs/brazil-case-law-mcp). This
repository holds its listing for MCP registries; the server is not installed locally.

## Connect

Through Apify's MCP server, with browser sign-in (OAuth):

```
https://mcp.apify.com/?tools=siteacs/brazil-case-law-mcp
```

Or directly, with an Apify API token ([get one](https://console.apify.com/settings/integrations)):

```json
{
  "mcpServers": {
    "brazil-case-law": {
      "url": "https://siteacs--brazil-case-law-mcp.apify.actor/mcp",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

An autonomous agent with no account can buy a prepaid, spend-capped token at [agi.apify.com](https://agi.apify.com).

## The tool

`search_brazil_case_law`: `query` (legal terms in Portuguese, with AND, OR, NOT and quotes), `party` (a party or
lawyer's name), `cnpj` (a company CNPJ; sole traders are refused), `court` (`STJ`, `STF` or both), `decision_type`,
`date_from`, `date_to`, `relator`, `case_class`, `max_results` (1 to 20) and `include_full_text`.

Example: `{"query": "\"dano moral\" bagagem extravio", "court": "STJ", "max_results": 5}`

## Price

$0.02 per search, $0.06 per search with full text, billed by Apify. No monthly fee from us.

## Sources and limits

Official published decisions only, read from the courts' public search services. Searching by a person's CPF is not
offered. Details, output fields and limits: [the Apify page](https://apify.com/siteacs/brazil-case-law-mcp).
