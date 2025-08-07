# Tracking Proxy

A lightweight nginx-based HTTP proxy that forwards client requests to Mixpanel's tracking API and JavaScript library endpoints.

This is a fork of the original [Mixpanel tracking-proxy repository](https://github.com/mixpanel/tracking-proxy) with enhanced IP forwarding capabilities.

## Purpose

This proxy server acts as an intermediary between client applications and Mixpanel's API endpoints, enabling tracking via proxy while preserving client IP addresses for accurate geolocation data.

## Features

- Proxies requests to Mixpanel's tracking API (`api.mixpanel.com`)
- Serves Mixpanel JavaScript libraries (`lib.js`, `lib.min.js`)
- Handles decision API calls (`/decide`)
- Sophisticated client IP preservation for geolocation tracking
- Support for Cloudflare and cloud provider IP forwarding
- Docker-ready deployment

## Quick Start

```bash
docker build -t tracking-proxy .
docker run -d -p 8080:80 tracking-proxy
```

Point your Mixpanel tracking to `http://your-proxy-domain:8080` instead of the default Mixpanel endpoints.
