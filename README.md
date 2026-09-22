# GunSpec API Examples

Runnable examples for the [GunSpec firearms API](https://gunspec.io) in TypeScript and Python: search and fetch firearm specifications, compare firearms, build a product page or a dashboard, export to a spreadsheet, balance a game's weapons, and receive webhooks.

These are the examples kept with the official SDKs' source, copied here on every stable release and pinned to the SDK version released with them.

## Get a key

Create an API key at [app.gunspec.io/keys](https://app.gunspec.io/keys), then put it in your environment. Both SDKs read it from there.

```bash
export GUNSPEC_API_KEY=your_key_here
```

## TypeScript

Uses [`@buun_group/gunspec-sdk`](https://www.npmjs.com/package/@buun_group/gunspec-sdk) 0.13.0. Node 18 or newer.

```bash
cd typescript
npm install
npm run basic-usage
```

| Example | What it shows | Plan it needs | Run |
| --- | --- | --- | --- |
| [`basic-usage.ts`](typescript/basic-usage.ts) | Search, fetch and compare firearms, and handle the errors the API returns. | Builder | `npm run basic-usage` |
| [`dashboard.ts`](typescript/dashboard.ts) | Build a firearms industry dashboard. | Enterprise | `npm run dashboard` |
| [`excel-report.ts`](typescript/excel-report.ts) | Generate a comprehensive firearms report for Excel/CSV export. | Explorer | `npm run excel-report` |
| [`game-dev.ts`](typescript/game-dev.ts) | Game developer weapon system integration. | Studio | `npm run game-dev` |
| [`product-page.ts`](typescript/product-page.ts) | Populate a product page for a specific firearm. | Builder | `npm run product-page` |

## Python

Uses [`gunspec`](https://pypi.org/project/gunspec/) 0.7.0. Python 3.9 or newer.

```bash
cd python
pip install -r requirements.txt
python basic_usage.py
```

| Example | What it shows | Plan it needs | Run |
| --- | --- | --- | --- |
| [`basic_usage.py`](python/basic_usage.py) | Basic usage of the gunspec SDK. | Builder | `python basic_usage.py` |
| [`webhooks.py`](python/webhooks.py) | Receive and verify GunSpec webhook deliveries. | None, it makes no API call | `python webhooks.py` |

The webhooks example only receives deliveries. Registering the endpoint it listens on (`client.webhooks.create`) needs: Any plan, with a key on your account.

## Which plan an example needs

Each "Plan it needs" is the highest plan any call in that example requires, read from the API's [OpenAPI spec](https://api.gunspec.io/openapi.json) rather than written by hand. On a lower plan, a call above yours is refused with a 403 whose `error.reason` says why. Listing firearms needs: Explorer. Compare plans on the [pricing page](https://gunspec.io/en/pricing).

## Straight from the terminal

```bash
curl "https://api.gunspec.io/v1/firearms?category=pistol" \
  -H "X-API-Key: $GUNSPEC_API_KEY"
```

## Links

- Documentation and API reference: [docs.gunspec.io](https://docs.gunspec.io)
- TypeScript SDK source: [gunspec-js](https://github.com/gunspec/gunspec-js)
- Python SDK source: [gunspec-python](https://github.com/gunspec/gunspec-python)
- MCP server for AI agents: [gunspec-mcp](https://github.com/gunspec/gunspec-mcp)

Use of the API is covered by the [GunSpec terms](https://gunspec.io/terms).
