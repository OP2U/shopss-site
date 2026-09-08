# SHOPSS Site v2.9

Personal site for https://shopss.me.

## v2.9

- Added SHOPSS Sentinel to the live systems panel and Projects section.
- Added a dedicated SHOPSS Sentinel portfolio page.
- Added live sanitized Sentinel telemetry from `/data/sentinel-summary.json`.
- Added Host Health, Threat Activity, security-event, SSH-source, brute-force-alert, and block counters.
- Public Sentinel telemetry does not expose source IPs, attempted usernames, raw logs, credentials, internal paths, webhook data, or firewall rules.
- Added `data/.gitignore` so the generated live telemetry file is never committed.
- Preserved the existing v2.8 visual design and infrastructure section.

## v2.8

- Replaced the SHOPSS Desktop project preview with the latest ultrawide screenshot.
- Removed the Steam link from the homepage.
- Redesigned the **What runs it** section into a layered infrastructure overview.
- Added DigitalOcean/Ubuntu, Nginx/Let's Encrypt, GitHub/systemd, C#/WPF/.NET 10, Python/Discord, SQLite/monitoring, Cloudflare analytics, and Inno Setup references.

The production site is automatically deployed from the `main` branch of:

https://github.com/OP2U/shopss-site
