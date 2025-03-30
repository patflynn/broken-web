# broken.dev Website

A minimalist terminal-inspired website.

## Development

See [CLAUDE.md](CLAUDE.md) for development guidelines and commands.

## Deployment

This repository uses GitHub Actions to automatically deploy to Google Cloud Storage when changes are merged to the main branch.

### Required Secrets

To enable automatic deployments, you'll need to set up the following GitHub repository secrets:

- `GCP_PROJECT_ID`: Your Google Cloud project ID
- `GCP_SA_KEY`: Base64-encoded service account key JSON with Storage Admin permissions
- `GCS_BUCKET_NAME`: The name of your Google Cloud Storage bucket

### Service Account Setup

1. Create a service account in Google Cloud Console
2. Assign it the Storage Admin role
3. Create and download a JSON key
4. Base64 encode the key file: `cat key-file.json | base64 -w 0`
5. Add the encoded string as the `GCP_SA_KEY` secret in GitHub