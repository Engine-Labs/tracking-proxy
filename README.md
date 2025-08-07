# Mixpanel Tracking Proxy

This repository contains an Nginx-based proxy server for Mixpanel analytics. It allows you to route Mixpanel tracking requests through your own domain, helping bypass ad-blockers and content filtering that may block direct connections to Mixpanel's API endpoints.

## Purpose

- **Bypass ad-blockers**: Route analytics through your domain instead of `mixpanel.com`
- **Improve data collection**: Reduce tracking losses from privacy tools and browser extensions
- **First-party data collection**: Collect analytics data as first-party requests from your domain
- **Enhanced IP handling**: Properly forward client IP addresses for accurate geo-location data

## What it proxies

- Mixpanel JavaScript library endpoints (`/lib.js`, `/lib.min.js`)
- Analytics ingestion API (`/track`, `/engage`, etc.)
- Feature flag decision API (`/decide`)

The proxy is configured to handle Cloudflare and other CDN scenarios with comprehensive IP forwarding and debug headers for troubleshooting.
