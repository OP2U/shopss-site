# SHOPSS Site Starter

A simple static site designed to run alongside your existing Discord bot on your DigitalOcean VPS.

## Files

- `index.html`
- `styles.css`
- `assets/shopss-logo.png`

## Before deploying

Open `index.html` and replace:

`YOUR_GITHUB_URL`

with your real GitHub profile URL.

## Deploy on Ubuntu with Nginx

The following assumes your existing CS2 bot is already running through systemd and that nothing else is currently using port 80.

Install Nginx:

```bash
sudo apt update
sudo apt install -y nginx
```

Create the website folder:

```bash
sudo mkdir -p /var/www/shopss
```

Upload/copy the contents of this project into:

```text
/var/www/shopss
```

Create an Nginx site:

```bash
sudo nano /etc/nginx/sites-available/shopss
```

Paste:

```nginx
server {
    listen 80;
    listen [::]:80;

    server_name _;

    root /var/www/shopss;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Enable it:

```bash
sudo rm -f /etc/nginx/sites-enabled/default
sudo ln -s /etc/nginx/sites-available/shopss /etc/nginx/sites-enabled/shopss
sudo nginx -t
sudo systemctl reload nginx
```

Then open your DigitalOcean public IP in a browser.

## Later: custom domain + HTTPS

Once you buy a domain, change `server_name _;` to your domain and point the domain's DNS A record at your VPS.

At that point we can add HTTPS with Let's Encrypt / Certbot, or switch the site to Caddy for automatic certificates.
