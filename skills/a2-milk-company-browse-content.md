---
name: a2-milk-company-browse-content
description: Browse or filter articles and recipes published on The a2 Milk Company Careers site.
api: a2-milk-company:careers-public-api
operations:
- listArticles
- listRecipes
---
# Browse articles and recipes

1. For articles and guides call `listArticles` (POST /api/article-listing) with `{"searchTerm": "", "page": 0, "limit": 10}`. An empty `searchTerm` returns everything.
2. For recipes call `listRecipes` (POST /api/recipe-listing) with the same body shape.
3. Page through with the zero-based `page` index until results run out.

Rules: read-only listing calls despite the POST verb; no authentication. MCP equivalents: `list_articles`, `list_recipes` (they take `query` instead of `searchTerm`).
