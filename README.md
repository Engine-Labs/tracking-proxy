# 🔄 Tracking Proxy

A lightweight Nginx-based proxy server for analytics tracking that forwards requests to analytics service endpoints while preserving client information and bypassing common tracking restrictions.

## ✨ What it does

This proxy server acts as an intermediary between client applications and analytics services (specifically Mixpanel), providing:

- **📍 IP Preservation**: Maintains original client IP addresses for accurate geo-location tracking
- **🛡️ Ad-blocker Bypass**: Routes tracking requests through your domain to avoid ad-blocker restrictions
- **🔀 Request Forwarding**: Proxies requests to:
  - 📊 Analytics ingestion API endpoints
  - 📜 JavaScript tracking libraries
  - ⚙️ Decision/configuration endpoints

## 🔧 How it works

The proxy uses Nginx to forward requests to the appropriate analytics service endpoints:

- `/` - Routes to the main analytics API for event ingestion
- `/lib.js` and `/lib.min.js` - Serves analytics JavaScript libraries
- `/decide` - Handles analytics configuration and feature flag requests

The configuration includes special handling for Cloudflare and various hosting providers to ensure client IP addresses are properly forwarded for geo-location tracking.

## 🚀 Deployment

The project includes a Dockerfile for containerized deployment and configuration files for various cloud providers. Simply deploy the Docker container or copy the Nginx configuration to your existing server.

---

*This project is a fork of the original Mixpanel tracking proxy.*
