# GitHub Actions Workflows

## Docker Build and Push to DigitalOcean Registry

This workflow builds the n8n Docker image and pushes it to your DigitalOcean container registry.

### Setup Instructions

1. Generate a DigitalOcean API token with read and write permissions:
   - Go to your DigitalOcean account → API → Generate New Token
   - Make sure it has both read and write scopes
   - Copy the token

2. Add the token as a GitHub repository secret:
   - Go to your GitHub repository → Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `DIGITALOCEAN_ACCESS_TOKEN`
   - Value: Paste your DigitalOcean token
   - Click "Add secret"

3. Make sure your DigitalOcean registry is already created:
   - If not, create it in the DigitalOcean console under "Container Registry"
   - Name: `replikate-sg`

### Workflow Trigger

The workflow runs:
- On push to the `master` branch
- When you create version tags (`v*`)
- Manually via GitHub Actions UI (workflow_dispatch)

### Image Tags

The workflow creates several Docker tags:
- Branch name (e.g., `master`)
- Version tag (when pushing a tag like `v1.2.3`)
- Major.Minor version (e.g., `1.2` for tag `v1.2.3`)
- Short SHA commit hash
- `latest` tag for the default branch