---
"@shunkakinoki/setup-bun": minor
---

Initial release of setup-bun action

This changeset releases the setup-bun GitHub Action as v1. The action provides:

- Bun runtime setup using oven-sh/setup-bun@v2
- Optional dependency installation with caching
- Support for custom working directories and Bun versions
- Turbo cache support for improved build performance
- Proper branding and metadata for GitHub Marketplace

Users can now consume this action using:
```yaml
uses: shunkakinoki/actions/setup-bun@v1
```
