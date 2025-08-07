# Mixpanel Tracking Proxy

A lightweight nginx-based reverse proxy for Mixpanel's tracking API and JavaScript library endpoints. This forked repository provides a containerized solution for proxying Mixpanel requests, enabling:

- **Client IP preservation** for accurate geolocation tracking
- **Multi-region support** with configurable endpoints (US, EU, IN data residency)
- **Easy deployment** via Docker or cloud platforms
- **High performance** nginx configuration optimized for tracking workloads

## Quick Start

**Docker:**
```bash
docker build -t mixpanel-proxy .
docker run -d -p 8080:80 mixpanel-proxy
```

**Configuration:**
The nginx configuration proxies the following endpoints:
- `/lib.min.js`, `/lib.js` → Mixpanel JavaScript libraries
- `/decide` → Mixpanel decide API
- `/` → Main Mixpanel ingestion API

For detailed configuration and deployment options, see the original [Mixpanel tracking-proxy documentation](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
