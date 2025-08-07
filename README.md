# Mixpanel Tracking Proxy

A lightweight nginx-based HTTP proxy server that acts as an intermediary between client applications and Mixpanel's tracking API endpoints.

## What This Does

This proxy server forwards tracking requests to Mixpanel while preserving client IP addresses for accurate geolocation tracking. It handles:

- **JavaScript Library Requests** (`/lib.min.js`, `/lib.js`) - Proxies to Mixpanel's CDN
- **Feature Flag Requests** (`/decide`) - Proxies to Mixpanel's decide API
- **Tracking Events** (`/`) - Proxies all other requests to Mixpanel's ingestion API

## Quick Start

### Docker Deployment

```bash
git clone https://github.com/Engine-Labs/tracking-proxy.git
cd tracking-proxy
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

### Cloud Deployment

Deploy directly to your preferred cloud provider using the configuration files included in this repository:

- **Docker**: Use the included `Dockerfile`
- **Render**: Use `render.yaml` 
- **Digital Ocean**: Use `.do/app.yaml`

## Configuration

- **US Data Center**: Default configuration (api.mixpanel.com)
- **EU Data Residency**: Change endpoint to `api-eu.mixpanel.com` in nginx.conf
- **IN Data Residency**: Change endpoint to `api-in.mixpanel.com` in nginx.conf

The proxy includes IP forwarding logic for Cloudflare and other reverse proxy setups to ensure accurate geolocation tracking.

---

*This is a fork of the original [Mixpanel tracking-proxy](https://github.com/mixpanel/tracking-proxy) repository.*
