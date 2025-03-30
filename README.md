# broken.dev Website

A minimalist terminal-inspired website.

## Project Structure

- **public/** - Contains all files that are deployed to the website
  - HTML files
  - CSS files
- **config/** - Contains configuration files not deployed to the website
  - CORS configuration
- **CLAUDE.md** - Development guidelines
- **.github/** - CI/CD workflows

## Development

See [CLAUDE.md](CLAUDE.md) for development guidelines and commands.

## Deployment

This repository uses GitHub Actions to automatically deploy the contents of the `public/` directory to Google Cloud Storage when changes are merged to the main branch.

### Required Secrets

To enable automatic deployments, you'll need to set up the following GitHub repository secrets:

- `GCP_PROJECT_ID`: Your Google Cloud project ID
- `GCS_BUCKET_NAME`: The name of your Google Cloud Storage bucket

### Workload Identity Federation Setup

This repository uses Workload Identity Federation with the `broken-web-github-deployer@broken-dev.iam.gserviceaccount.com` service account and the following Workload Identity Provider:
```
projects/411022031947/locations/global/workloadIdentityPools/dev-workflows-pool/providers/github-workflows
```

1. Create the service account in Google Cloud Console
2. Configure Workload Identity Federation to allow GitHub Actions to impersonate the service account
3. Assign the service account the Storage Admin role