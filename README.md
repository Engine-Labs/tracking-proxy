# Mixpanel Tracking Proxy (Fork)

This is a forked version of the Mixpanel tracking proxy server. It provides a lightweight nginx-based HTTP proxy that acts as an intermediary between client applications and Mixpanel's API endpoints.

## Purpose

This fork serves as a customized Mixpanel tracking proxy solution that:
- Proxies requests to Mixpanel's Ingestion API and JavaScript library endpoints
- Preserves client IP addresses for accurate geolocation tracking
- Supports multiple deployment options including Docker containerization
- Provides a foundation for custom proxy configurations and enhancements

## Quick Start

Build and run with Docker:
```bash
docker build -t mixpanel-proxy .
docker run --name tracking-proxy -d -p 8080:80 mixpanel-proxy
```

For detailed configuration options and deployment instructions, refer to the [original Mixpanel tracking-proxy documentation](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
