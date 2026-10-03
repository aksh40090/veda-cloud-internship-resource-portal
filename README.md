# Veda Technology Cloud-Based Internship Resource Portal

## Overview
A lightweight, responsive cloud-ready resource portal for internship domains, project information, FAQs and public learning resources.

## Requirements covered
- Veda Technology branded portal
- Internship domain listing
- Project information section
- FAQ/resource section
- Search/filtering
- Cloud-hosted website configuration
- Object-storage integration pattern (Cloudflare R2)
- Serverless function/API endpoint (Cloudflare Worker)
- Custom domain and HTTPS deployment documentation
- Architecture diagram
- Deployment documentation
- GitHub validation workflow

## Architecture
```text
Browser
  |
DNS + HTTPS
  |
Cloudflare Pages
  |--------------------|
Static UI            /api/*
  |                    |
JSON data       Cloudflare Worker
                       |
                Resource metadata
                       |
                Optional R2 storage
```

## Run locally
```bash
python -m http.server 8000
```
Open `http://localhost:8000`.

## GitHub
Create a public repository, upload the project, and keep the `main` branch as the deployment branch.

## Cloudflare Pages
Connect the GitHub repository to Cloudflare Pages. Use the repository root as the project directory. No build command is required for this static prototype.

## Worker
```bash
npm install -g wrangler
wrangler login
wrangler deploy
```
Endpoints:
- `GET /api/resources`
- `GET /api/resource?id=cloud`

After deployment, update `_redirects` with the real Worker URL.

## R2
Create an R2 bucket for selected public/non-sensitive resources. Add the R2 binding in `wrangler.toml` only after creating the bucket. Do not upload private intern data or secrets.

## DNS and HTTPS
Use the Cloudflare Pages custom-domain flow for the final domain. Verify that the published site loads through HTTPS.

## Privacy
This is a learning prototype. It must not be connected to private intern records or a production internship dashboard.

## Evidence
Take real screenshots after deployment: Pages deployment, published portal, search/filter, Worker JSON endpoint, R2 if used, and HTTPS/custom-domain configuration.
