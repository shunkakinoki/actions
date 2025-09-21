# @shunkakinoki/setup-bun

## 1.1.0

### Minor Changes

- [#1](https://github.com/shunkakinoki/actions/pull/1) [`d729dc4`](https://github.com/shunkakinoki/actions/commit/d729dc4a48440798e2e91212b06dc0ce45ab32fc) Thanks [@shunkakinoki](https://github.com/shunkakinoki)! - Initial release of setup-bun action

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
