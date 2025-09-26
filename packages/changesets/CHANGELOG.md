# @shunkakinoki/changesets

## 1.2.0

### Minor Changes

- [#30](https://github.com/shunkakinoki/actions/pull/30) [`957c2f0`](https://github.com/shunkakinoki/actions/commit/957c2f0708bbc0cda621b66160a59486b1712e35) Thanks [@shunkakinoki](https://github.com/shunkakinoki)! - Bump all packages to align versioning

## 1.1.0

### Minor Changes

- [#15](https://github.com/shunkakinoki/actions/pull/15) [`c0c747b`](https://github.com/shunkakinoki/actions/commit/c0c747bacbbd6d3b84683b9cee4a252d5a8f4952) Thanks [@copilot-swe-agent](https://github.com/apps/copilot-swe-agent)! - Initial release of changesets action

  This changeset releases the changesets GitHub Action as v1. The action provides:

  - Composite action wrapper around the official changesets/action
  - Bun runtime setup integration for optimal performance
  - Automated changeset status checks on pull requests
  - Configurable version and publish commands
  - Support for NPM token authentication and GitHub releases
  - Flexible commit modes (git-cli or github-api)
  - Optional GitHub release creation after publishing

  Users can now consume this action using:

  ```yaml
  uses: shunkakinoki/actions/changesets@v1
  with:
    github-token: ${{ secrets.GITHUB_TOKEN }}
    npm-token: ${{ secrets.NPM_TOKEN }}
  ```

  The action integrates seamlessly with the repository's Bun-based workflow and provides enhanced changesets functionality for versioning and publishing packages in monorepos.
