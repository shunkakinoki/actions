# actions
Shared actions for personal repositories

## Available Actions

### Changesets
Automated versioning and publishing using [Changesets](https://github.com/changesets/changesets).

**Authentication**: This action requires a `PAT_TOKEN` secret for full functionality. See [PAT_TOKEN Setup Guide](./PAT_TOKEN_SETUP.md) for detailed configuration instructions.

**Basic Usage**:
```yaml
- name: Run Changesets
  uses: ./.github/actions/changesets
  with:
    github-token: ${{ secrets.PAT_TOKEN }}
```

### Setup Bun
Sets up Bun runtime with dependency installation and caching.

### Auto Approve & Auto Merge  
Automated PR approval and merging for trusted changes.

## Documentation

- [PAT_TOKEN Setup Guide](./PAT_TOKEN_SETUP.md) - Required for changesets action
