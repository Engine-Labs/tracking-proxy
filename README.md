# Mixpanel Tracking Proxy

A lightweight nginx-based reverse proxy for Mixpanel analytics that routes tracking requests through your own domain to bypass ad blockers and improve data collection reliability.

## What This Does

This proxy server acts as an intermediary between your web applications and Mixpanel's API endpoints:

- **Proxy Routes**: Routes requests to Mixpanel's tracking API (`api.mixpanel.com`) and JavaScript library CDN (`cdn.mxpnl.com`)
- **Ad Blocker Bypass**: Serves tracking requests from your domain instead of Mixpanel's, preventing ad blockers from interfering
- **IP Preservation**: Maintains accurate client IP addresses for proper geolocation tracking
- **Multi-Region Support**: Configurable for US, EU, and IN data residency requirements

## Quick Start

**Using Docker:**
```bash
git clone <your-repo-url>
cd tracking-proxy
docker build -t mixpanel-proxy .
docker run -d -p 8080:80 mixpanel-proxy
```

**Testing the proxy:**
Visit `http://localhost:8080` - you should see a Mixpanel API welcome message.

## Configuration

The main configuration is in `nginx.conf`. Key settings:
- Change `api.mixpanel.com` to `api-eu.mixpanel.com` for EU data residency
- Change `api.mixpanel.com` to `api-in.mixpanel.com` for India data residency
- IP forwarding logic handles Cloudflare and cloud provider IP detection

## Usage

Point your Mixpanel client library to use your proxy domain instead of Mixpanel's default endpoints. This ensures tracking requests go through your server, avoiding ad blocker interference while maintaining full analytics functionality.
