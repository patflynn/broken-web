# broken.dev Website

A minimalist terminal-inspired website.

## Development

See [CLAUDE.md](CLAUDE.md) for development guidelines and commands.

## Deployment

This repository uses GitHub Actions to automatically deploy to Google Cloud Storage when changes are merged to the main branch.

### Required Secrets

To enable automatic deployments, you'll need to set up the following GitHub repository secrets:

- `GCP_PROJECT_ID`: Your Google Cloud project ID
- `WORKLOAD_IDENTITY_PROVIDER`: Your Workload Identity Provider (format: `projects/123456789/locations/global/workloadIdentityPools/my-pool/providers/my-provider`)
- `GCS_BUCKET_NAME`: The name of your Google Cloud Storage bucket

### Workload Identity Federation Setup

This repository uses Workload Identity Federation with the `broken-web-github-deployer@broken-dev.iam.gserviceaccount.com` service account.

1. Create the service account in Google Cloud Console
2. Configure Workload Identity Federation to allow GitHub Actions to impersonate the service account
3. Assign the service account the Storage Admin role
4. Set up your Workload Identity Provider and add it to the GitHub secrets