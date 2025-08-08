# Mixpanel Tracking Proxy

A lightweight nginx-based HTTP proxy server for Mixpanel tracking API, forked and customized for enhanced tracking capabilities.

## Overview

This proxy acts as an intermediary between client applications and Mixpanel's API endpoints, enabling:

- **Tracking API Proxy**: Forwards requests to `api.mixpanel.com` with proper header management
- **JavaScript Library Proxy**: Serves Mixpanel's client libraries via `/lib.js` and `/lib.min.js`
- **Decision API Proxy**: Handles feature flag requests via `/decide` endpoint
- **IP Preservation**: Maintains accurate geolocation tracking through sophisticated IP forwarding
- **Multi-Region Support**: Configurable for EU and IN data residency requirements

## Quick Start

### Docker Deployment
```bash
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

### Configuration
The nginx configuration includes:
- Cloudflare and Render.com IP range support
- Debug headers for troubleshooting
- High-performance settings with connection backlog optimization

## Features

- **Client IP Preservation**: Advanced IP detection and forwarding logic
- **Debug Logging**: Comprehensive request debugging capabilities  
- **Load Balancing Ready**: Optimized for high-concurrency environments
- **Cloud Provider Agnostic**: Works across different hosting platforms

Forked from the original Mixpanel tracking proxy with enhanced debugging and IP handling capabilities.
