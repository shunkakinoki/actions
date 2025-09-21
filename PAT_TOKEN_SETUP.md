# PAT_TOKEN Setup Guide for Changesets Action

This guide explains how to configure a Personal Access Token (PAT_TOKEN) for the Changesets action when `secrets.GITHUB_TOKEN` has insufficient permissions.

## Why Use PAT_TOKEN?

The default `GITHUB_TOKEN` provided by GitHub Actions has limited permissions and may fail when:

- Accessing GraphQL API endpoints required by changesets
- Working with private repositories or organization-level resources
- Publishing to GitHub Package Registry
- Creating GitHub releases with enhanced metadata

## Required Permissions

Your PAT_TOKEN must have the following scopes:

### Essential Scopes
- `repo` - Full control of private repositories
- `write:packages` - Upload packages to GitHub Package Registry
- `read:org` - Read organization membership for GraphQL queries

### Optional Scopes (recommended)
- `workflow` - Update GitHub Actions workflows (if changesets modifies workflow files)
- `write:discussion` - Create and update discussions related to releases

## Setup Instructions

### 1. Create Personal Access Token

1. Go to GitHub → Settings → Developer Settings → Personal Access Tokens
2. Click "Generate new token (classic)" or "Fine-grained tokens" (for organization repos)
3. Select the required scopes listed above
4. Set appropriate expiration date
5. Click "Generate token" and copy the token value

### 2. Add Token to Repository Secrets

1. Go to your repository → Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Name: `PAT_TOKEN`
4. Value: Paste your personal access token
5. Click "Add secret"

### 3. Update Workflow Configuration

The changesets workflow is already configured to use `PAT_TOKEN`. No changes needed.

### 4. Verify Token Permissions

The action includes built-in validation that will check:
- ✅ Token has access to repository
- ✅ Token credentials are valid
- ✅ Required API endpoints are accessible

If validation fails, check:
1. Token hasn't expired
2. All required scopes are selected
3. Token belongs to user with repository access

## Troubleshooting

### "Resource not accessible by personal access token"

**Cause**: Token missing required scopes
**Solution**: Regenerate token with all required permissions

### "Bad credentials" error

**Cause**: Invalid or expired token
**Solution**: Generate new token and update PAT_TOKEN secret

### GraphQL API errors

**Cause**: Missing `read:org` permission for organization repositories
**Solution**: Add `read:org` scope to token

### Package publishing fails

**Cause**: Missing `write:packages` permission
**Solution**: Add `write:packages` scope to token

## Security Best Practices

1. **Use fine-grained tokens** when possible for organization repositories
2. **Set minimal expiration** and rotate tokens regularly
3. **Use repository-specific tokens** rather than broad organization access
4. **Monitor token usage** in GitHub's token settings page

## Fallback to GITHUB_TOKEN

If PAT_TOKEN is not available or has issues, you can temporarily revert to GITHUB_TOKEN by changing the workflow:

```yaml
# In .github/workflows/changesets.yml
with:
  github-token: ${{ secrets.GITHUB_TOKEN }}  # Instead of PAT_TOKEN
```

Note: Some advanced changesets features may not work with the default GITHUB_TOKEN.