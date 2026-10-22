---
name: a2-milk-company-search-site
description: Find pages on The a2 Milk Company Careers site by full-text search, then read the hit as Markdown.
api: a2-milk-company:careers-public-api
operations:
- searchSite
- getSitemap
---
# Search The a2 Milk Company Careers site

1. Call `searchSite` (PUT /api/search) with a JSON body `{"searchTerm": "...", "page": 0, "limit": 10}`. `page` is zero-based. Optional `filters` takes an Algolia filter expression; `sortBy` accepts `alphabetical`.
2. Read a result page by GET-ing its URL with `Accept: text/markdown` (every HTML page serves Markdown; `Vary: Accept` is set). The MCP equivalent is the `get_page` tool.
3. If a URL is unknown, resolve it against `getSitemap` (GET /sitemap.xml). Unknown paths return a real 404 with a Markdown body, never a soft 200.

Rules: no authentication; read-only; no personal data is accepted. PUT here is a query, not a write. The site does not handle order status or medical advice.
