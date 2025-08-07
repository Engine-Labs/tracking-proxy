# Mixpanel Tracking Proxy

A lightweight nginx-based proxy server that acts as an intermediary between client applications and Mixpanel's API endpoints. This proxy enables tracking through your own domain while preserving client IP addresses for accurate geolocation data.

## Overview

This forked tracking proxy provides:

- **Reverse proxy** for Mixpanel's ingestion API and JavaScript library endpoints
- **Client IP preservation** for accurate geolocation tracking
- **Data residency support** for EU and IN regions
- **Cloud-agnostic deployment** with multiple deployment options

## Quick Deploy

Deploy instantly to your preferred cloud provider:

[![Google Cloud](https://binbashbanana.github.io/deploy-buttons/buttons/remade/googlecloud.svg)](https://deploy.cloud.run)
[![Digital Ocean](https://www.deploytodo.com/do-btn-blue.svg)](https://cloud.digitalocean.com/apps/new?repo=https://github.com/mixpanel/tracking-proxy/tree/master)
[![Railway](https://binbashbanana.github.io/deploy-buttons/buttons/remade/railway.svg)](https://railway.app/template/_RaWSW)
[![Render](https://binbashbanana.github.io/deploy-buttons/buttons/remade/render.svg)](https://render.com/deploy?repo=https://github.com/mixpanel/tracking-proxy)

## Docker Usage

```bash
docker build -t mixpanel-proxy .
docker run --name tracking-proxy -d -p 8080:80 mixpanel-proxy
```

Visit `http://localhost:8080` to verify the proxy is working.

## Configuration

- **EU Data Residency**: Change `api.mixpanel.com` to `api-eu.mixpanel.com` in nginx.conf
- **IN Data Residency**: Change `api.mixpanel.com` to `api-in.mixpanel.com` in nginx.conf

For detailed configuration and troubleshooting, see the [Mixpanel Tracking via Proxy documentation](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
