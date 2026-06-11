# Herculean Technologies Website

## Deploy With GitHub Pages

The repository includes `.github/workflows/deploy-pages.yml`. Push the repository to GitHub using the `main` branch, then enable **GitHub Pages → Source → GitHub Actions** in the repository settings.

The workflow publishes `outputs/company-website` whenever `main` is updated. On GitHub Pages, the lead form opens a pre-addressed email to `sales@herculeantechnologies.com` because GitHub Pages cannot run server-side email code.

## Run With The Email Backend

Run the site and lead intake backend:

```sh
node server.mjs
```

Lead intake posts to `/api/leads`. Each request is saved to `data/leads.jsonl` and, when SMTP is configured, emailed to `sales@herculeantechnologies.com`.

Set these environment variables before starting the server:

```sh
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=your-smtp-user
SMTP_PASS=your-smtp-password
SMTP_FROM=no-reply@herculeantechnologies.com
```

Optional:

```sh
PORT=4173
SMTP_SECURE=true
```
