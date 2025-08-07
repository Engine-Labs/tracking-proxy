# 🚀 Mixpanel Tracking Proxy

A lightweight nginx-based HTTP proxy server that acts as an intermediary between your applications and Mixpanel's tracking API endpoints.

## 🔄 What it does

This proxy forwards tracking requests from your applications to Mixpanel while preserving client IP addresses for accurate geolocation tracking. It handles requests to:

- 📄 `/lib.min.js` and `/lib.js` - Mixpanel JavaScript library files
- 🎯 `/decide` - Mixpanel's feature flag and A/B testing endpoint  
- 🌐 `/` - All other Mixpanel API endpoints (tracking, ingestion, etc.)

## ✨ Why use a proxy

- 🌍 **Client IP preservation**: Maintains accurate geolocation data in your Mixpanel events
- 🛡️ **Avoid ad blockers**: Routes tracking through your own domain instead of mixpanel.com
- 🏛️ **Data residency compliance**: Configurable endpoints for EU and IN data residency requirements
- 🔗 **First-party tracking**: Enables tracking from your own domain for better reliability

## ⚡ Quick start

Deploy with one click:

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/mixpanel/tracking-proxy)

Or run with Docker:
```bash
git clone https://github.com/mixpanel/tracking-proxy
cd tracking-proxy
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

For detailed setup instructions and configuration options, see the [Mixpanel documentation on Tracking via Proxy](https://docs.mixpanel.com/docs/tracking/how-tos/tracking-via-proxy).
