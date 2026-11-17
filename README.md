# Klusvang MCP server

A public, key-less [Model Context Protocol](https://modelcontextprotocol.io) server with counts of Dutch building-permit notices (omgevingsvergunningen), built from the official bulletins on officielebekendmakingen.nl (CC0). Run by ProductTickler B.V. as part of [Klusvang](https://klusvang.nl).

- URL: `https://klusvang.nl/api/mcp` (streamable HTTP, POST, no authentication)
- Registry name: `nl.klusvang/mcp`
- Docs: https://klusvang.nl/ontwikkelaars
- Support: support@klusvang.nl

## Tools (read only, aggregate counts only)

- `find_municipality`: find the URL slug of a Dutch municipality by name.
- `municipality_permit_counts`: notices of one municipality in the last 60 and 30 days, by work type, plus its rank in the latest closed month.
- `province_permit_counts`: notices in one province by work type, with the municipalities that published the most.
- `work_type_nationwide`: one work type (for example dakkapel, aanbouw, kozijnen) across all municipalities.
- `bouwmonitor_month`: the frozen monthly national count with a ranking of municipalities.

No addresses, names or free-text permit search. Counts from 1 to 4 per municipality are reported as "fewer than 5". Limit: 20 uncached calls per minute per client.

## Connect

Claude Code: `claude mcp add --transport http klusvang https://klusvang.nl/api/mcp`

Claude and ChatGPT web: add a custom connector with the URL above, no authentication.

## Licence

This README is MIT licensed. The server itself is a hosted service; the data comes from public sources, see https://klusvang.nl/ontwikkelaars.
