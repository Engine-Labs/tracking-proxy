# Nginx Proxy Server

A lightweight, containerized Nginx proxy server with optimized configuration for handling API requests and static assets.

## Features

- Dockerized nginx server with custom configuration
- Real IP detection and forwarding for Cloudflare and other CDNs
- Comprehensive request logging and debugging headers
- Ready for deployment on various cloud platforms

## Quick Start

### Using Docker

1. Build the image:
   ```bash
   docker build -t nginx-proxy .
   ```

2. Run the container:
   ```bash
   docker run -p 8080:80 nginx-proxy
   ```

3. The proxy will be available at `http://localhost:8080`

### Configuration

The nginx configuration can be customized by modifying `nginx.conf` to suit your specific proxy requirements.

## Deployment

This project includes configuration files for easy deployment to various cloud platforms:
- Render.com (`render.yaml`)
- Heroku-compatible (`app.json`)
- Docker-based deployment (`Dockerfile`)

---

*This project provides a clean, production-ready nginx proxy solution.*
