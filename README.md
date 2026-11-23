# Empire Security MCP client examples

Empire Security groups its scanning and audit tools by module. The product site lists the available modules.

This repository holds small, working examples for the hosted **Empire Security** MCP server. It is maintained by Elite AI Empire. The server itself is hosted; nothing here runs it.

- Product: https://security.eliteaiempire.com/
- MCP endpoint (streamable HTTP): `https://security.eliteaiempire.com/mcp`
- OpenAPI: https://security.eliteaiempire.com/openapi.json
- Pricing, machine readable: https://security.eliteaiempire.com/pricing.json
- Discovery file: https://security.eliteaiempire.com/.well-known/mcp.json

## Tools

| Tool | What it does |
|---|---|
| `scan_domain` | Passive, read-only check of a public domain: DNS, TLS certificate and security headers. Refuses names that are not public. |
| `insurance_pack` | Cyber-insurance questionnaire pack for a public domain: answers the questions a passive scan can see (email authentication, DMARC, HTTPS, HSTS) and names the ev |
| `get_company_info` | What this company sells, who it is for, and every agent/API entry point. No account needed. |
| `list_pricing` | Current plans and prices in USD: plan, interval, amount_usd, currency, what_you_get. No account needed. |
| `get_checkout_link` | Checkout URL for a plan. With no arguments: the main paid plan. Where the site supports it the URL is a Stripe-hosted Checkout session (created unpaid; a human  |
| `search_site` | Find pages on this site by keyword; returns url, title and summary. |

## Try it

```bash
bash examples/initialize.sh
python3 examples/client.py
```

`examples/client.py` uses only the Python standard library. It sends `initialize` and `tools/list` and prints the result. No key is needed for the public read tools. Tools that need an account say so in their description.

## Registry

Listed in the official MCP registry. Server manifest: `server.json`.

## Licence

MIT. See `LICENSE`.
