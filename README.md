# Mixpanel Tracking Proxy

A lightweight nginx-based HTTP proxy server that forwards client requests to Mixpanel's tracking API and JavaScript library endpoints.

## What it does

This proxy server acts as an intermediary between your applications and Mixpanel's services, enabling:
- Tracking API requests via your own domain
- JavaScript library delivery through proxy
- Client IP preservation for accurate geolocation tracking
- Support for EU and IN data residency requirements

## Quick Deploy

**One-click cloud deployment:**
- [Google Cloud](https://deploy.cloud.run)
- [Digital Ocean](https://cloud.digitalocean.com/apps/new?repo=https://github.com/mixpanel/tracking-proxy/tree/master)
- [Railway](https://railway.app/template/_RaWSW)
- [Render](https://render.com/deploy?repo=https://github.com/mixpanel/tracking-proxy)

**Docker:**
```bash
docker build -t mixpanel-proxy .
docker run -d -p 8080:80 mixpanel-proxy
```

**Manual:** Copy the nginx configuration locations to your existing nginx setup.

For detailed documentation, visit [Mixpanel's Tracking via Proxy docs](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
