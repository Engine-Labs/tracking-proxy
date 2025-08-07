# Mixpanel Tracking Proxy

A lightweight nginx-based proxy server that acts as an intermediary between client applications and Mixpanel's tracking API endpoints. This proxy enables reliable data collection while preserving client IP addresses for accurate geolocation tracking.

## What it does

This proxy forwards requests to:
- Mixpanel's JavaScript libraries (`/lib.js`, `/lib.min.js`)
- Feature flag decisions (`/decide`)
- Event tracking and ingestion APIs (`/`)

## Key Features

- **IP Preservation**: Maintains original client IP addresses through sophisticated header forwarding for accurate geolocation data
- **Cloud Provider Support**: Pre-configured for Cloudflare, Render.com, and other popular hosting platforms
- **Multi-Region**: Supports US, EU, and IN data residency requirements
- **High Performance**: Optimized nginx configuration with load balancing support
- **Easy Deployment**: Docker containerization with one-click cloud deployment options

## Quick Start

```bash
# Clone and run with Docker
git clone https://github.com/mixpanel/tracking-proxy
cd tracking-proxy
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

Point your Mixpanel tracking requests to `http://localhost:8080` instead of `https://api.mixpanel.com`.
