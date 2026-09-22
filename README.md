# GunSpec API Examples

Working code examples for the [GunSpec firearms API](https://gunspec.io) in TypeScript, Python and cURL. Look up firearm specifications, resolve loose names to records, compare firearms, check attachment compatibility, and connect an AI agent over MCP.

Every example runs against the live API at `https://api.gunspec.io`. The full reference and guides live at [docs.gunspec.io](https://docs.gunspec.io).

## What you can build

- **Product pages** that pull specs, calibers and images for any firearm
- **Search and autocomplete** that turn "G19 gen 5" into a single firearm record
- **Comparison tools** that put two or more firearms side by side
- **Fitment checks** that answer which attachments fit a given firearm
- **Dashboards and reports** built from catalogue statistics
- **Game balancing** from firearm stats and game profiles
- **AI agents** that answer firearm questions through the GunSpec MCP server

## Quick start

Get a free API key at [gunspec.io](https://gunspec.io), then set it in your environment:

```bash
export GUNSPEC_API_KEY=your_key_here
```

### TypeScript

```bash
npm install @buun_group/gunspec-sdk
```

```typescript
import { GunSpec } from '@buun_group/gunspec-sdk'

const client = new GunSpec()

const { data: hit } = await client.firearms.resolve('G19 gen 5')
if (hit.status === 'resolved') console.log(hit.firearmId)
```

### Python

```bash
pip install gunspec
```

```python
from gunspec import GunSpec

client = GunSpec()

result = client.firearms.list({"category": "pistol", "per_page": 5})
for firearm in result.data:
    print(firearm["id"], firearm["name"])
```

### cURL

```bash
curl "https://api.gunspec.io/v1/firearms?category=pistol" \
  -H "X-API-Key: $GUNSPEC_API_KEY"
```

## Examples

| Example | What it shows | Languages |
| --- | --- | --- |
| basic-usage | List, search and fetch firearms | TypeScript, Python |
| product-page | Build a firearm product page from one record | TypeScript |
| dashboard | Catalogue statistics for a dashboard | TypeScript |
| excel-report | Export firearm specs to a spreadsheet | TypeScript |
| game-dev | Game stats, balancing and tier lists | TypeScript |
| webhooks | Receive and verify catalogue change events | Python |
| mcp-agent | Connect Claude or another agent to the MCP server | Config |

Some endpoints need a paid plan. Each example names the plan it needs at the top of its README. See [pricing](https://gunspec.io/en/pricing).

## Use GunSpec from an AI agent

GunSpec runs a hosted MCP server, so Claude, Cursor and other MCP clients can query the catalogue directly.

```
https://mcp.gunspec.io/mcp-oauth
```

Setup for each client is in the [MCP guide](https://docs.gunspec.io/en/mcp).

## Links

- Website: [gunspec.io](https://gunspec.io)
- Documentation: [docs.gunspec.io](https://docs.gunspec.io)
- OpenAPI spec: [api.gunspec.io/openapi.json](https://api.gunspec.io/openapi.json)
- TypeScript SDK: [@buun_group/gunspec-sdk on npm](https://www.npmjs.com/package/@buun_group/gunspec-sdk)
- Python SDK: [gunspec on PyPI](https://pypi.org/project/gunspec/)

## Terms

Use of the API is covered by the [GunSpec terms](https://gunspec.io/en/terms).
