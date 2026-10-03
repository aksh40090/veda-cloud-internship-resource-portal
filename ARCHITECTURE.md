# Architecture Diagram

```text
                  Internet / Browser
                          |
                     DNS + HTTPS
                          |
                   Cloudflare Pages
                    /                          Static UI          /api/*
                  |                  |
          resources.json      Cloudflare Worker
                                     |
                              Resource metadata
                                     |
                               Optional R2
```

The architecture separates the static presentation layer from the serverless API and optional object-storage layer. No private internship data is required.
