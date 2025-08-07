# Mixpanel Tracking Proxy

A lightweight nginx-based HTTP proxy server that acts as an intermediary between client applications and Mixpanel's API endpoints. This proxy enables tracking via proxy while preserving client IP addresses for accurate geolocation data.

## What it does

This proxy server forwards requests to Mixpanel's services:
- `/lib.min.js` and `/lib.js` - Serves Mixpanel JavaScript libraries from CDN
- `/decide` - Proxies to Mixpanel's decide API endpoint
- `/` - Forwards all other requests to Mixpanel's main API

## Key Features

- **IP Preservation**: Advanced IP forwarding logic that maintains client IP addresses through proxy chains
- **Cloudflare Support**: Built-in Cloudflare IP range configuration for accurate client IP detection
- **Multi-Region Support**: Configurable endpoints for EU (`api-eu.mixpanel.com`) and IN (`api-in.mixpanel.com`) data residency
- **Debug Headers**: Comprehensive logging and debugging headers for troubleshooting
- **High Concurrency**: Optimized for high-traffic scenarios with load balancing configuration

## Quick Start

### Option 1: Docker (Recommended)

```bash
# Clone the repository
git clone <repository-url>
cd tracking-proxy

# Build and run
docker build -t mixpanel-proxy .
docker run --name tracking-proxy -d -p 8080:80 mixpanel-proxy

# Test the proxy
curl http://localhost:8080
```

### Option 2: One-Click Deploy

[![Google Cloud Btn]](https://deploy.cloud.run)
[![Digital Ocean Btn]](https://cloud.digitalocean.com/apps/new?repo=<repository-url>)
[![Railway Btn]](https://railway.app/template/_RaWSW)
[![Render Btn]](https://render.com/deploy?repo=<repository-url>)

[Google Cloud Btn]: https://binbashbanana.github.io/deploy-buttons/buttons/remade/googlecloud.svg
[Digital Ocean Btn]: https://www.deploytodo.com/do-btn-blue.svg
[Railway Btn]: https://binbashbanana.github.io/deploy-buttons/buttons/remade/railway.svg
[Render Btn]: https://binbashbanana.github.io/deploy-buttons/buttons/remade/render.svg

### Option 3: Manual nginx Configuration

Copy the location blocks from `nginx.conf` into your existing nginx configuration.

## Configuration

### Data Residency

For **EU Data Residency**: Change `api.mixpanel.com` to `api-eu.mixpanel.com` in `nginx.conf`
For **IN Data Residency**: Change `api.mixpanel.com` to `api-in.mixpanel.com` in `nginx.conf`

### IP Configuration

The proxy automatically handles IP forwarding for:
- Cloudflare (CF-Connecting-IP header)
- Render.com internal IPs
- Standard X-Forwarded-For headers

For other CDN providers, modify the IP detection logic in the nginx configuration.

## Verification

A working proxy should return the following when accessed directly:

```json
{
  "error": "Welcome. Get started with our API by visiting https://developer.mixpanel.com/"
}
```

## Documentation

For more details on tracking via proxy, visit [Mixpanel's documentation](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
