<div align="center">

<img src="docs/assets/logo.png" alt="VidGen Logo" width="320" style="border-radius: 20px; box-shadow: 0 4px 20px rgba(0,0,0,0.15);" />

<p><b>Out-of-the-box, High-Performance Full-Stack Open-Source AI Video & Image Generation Platform</b></p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Nuxt 3](https://img.shields.io/badge/Nuxt-3.21.11-00DC82?style=for-the-badge&logo=nuxt.js&logoColor=white)](https://nuxt.com/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.141.1-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Docker Compose](https://img.shields.io/badge/Docker%20Compose-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](docker-compose.yml)

[English](README.md) | [简体中文](README_CN.md)

</div>

<p align="center">
  <a href="https://vidgenerator.ai"><b>🚀 Live Demo</b></a> •
  <a href="#-1-minute-quick-start-docker"><b>⚡ Quick Start</b></a> •
  <a href="#-key-features"><b>✨ Features</b></a> •
  <a href="#️-connect-real-ai--payments"><b>⚙️ Integrations</b></a> •
  <a href="#-documentation"><b>📚 Docs</b></a>
</p>

---

> 🚀 **Battle-Tested in Production**: VidGen powers the commercial platform [vidgenerator.ai](https://vidgenerator.ai).

## 🌟 What is VidGen?

**VidGen** is an open-source, production-ready AI video and image generation platform designed for creators, indie hackers, and entrepreneurs.

Whether you want to launch a full-featured Midjourney / Luma alternative in **5 minutes** or build a custom AI monetization business, VidGen provides a **complete end-to-end solution**: from a modern SSR Nuxt 3 frontend portal, bilingual admin dashboard, and Celery async generation engine, to **credit economics, payment gateways, prompt community, virtual user generators, and content moderation**.

---

## ⚡ 1-Minute Quick Start (Docker)

No need to install Python/Node.js, configure databases, or **even apply for paid API keys** (built-in Mock generation mode and demo data for zero-cost local testing). Run the entire stack with a single command!

### 1. Clone and Launch

```bash
# 1. Clone repository
git clone https://github.com/ucmao/vidgen.git
cd vidgen

# 2. Launch all 6 services with Docker Compose (Web, Admin, FastAPI, Celery, Postgres, Redis)
docker compose up -d
```

### 2. Access Services

Once started, open your browser:

| Service | URL | Default Credentials / Note |
| :--- | :--- | :--- |
| 🌐 **User Web Portal** | `http://localhost:3000` | Preloaded with demo data & Mock AI engine for instant testing |
| 🔧 **Admin Panel** | `http://localhost:3001` | Username: `admin` (check terminal logs for the generated password, or set `INITIAL_ADMIN_PASSWORD`) |
| 🐍 **Interactive API Docs** | `http://localhost:8000/docs` | Swagger UI documentation & testing |

> 💡 **Quick Tips**:
> - View real-time startup logs: `docker compose logs -f backend`.
> - On initial container launch, database migrations and demo seed data are automatically applied.

---

## ✨ Key Features

### 🎨 Multi-Modal AI Generation
- **Text-to-Image (Text2Img)**: Generate high-resolution visuals via FLUX.1, SDXL, Midjourney, and more.
- **Image-to-Image (Img2Img)**: Image-guided synthesis with prompt tuning and strength control.
- **Text-to-Video (Text2Video)**: Turn prompts into dynamic AI video clips (HunyuanVideo, Luma, Pika, Runway).
- **Image-to-Video (Img2Video)**: Animate still photos into high-definition videos with motion control.

### 💰 Monetization & Credit Economics
- **Global Payments**: Native integration with **PayPal** and **Stripe** for subscriptions and credit top-ups.
- **Granular Credit Pricing**: Set custom credit deductions per model, resolution, and step.
- **Growth & Marketing**: Promo codes, discount campaigns, and tiered daily check-in streak rewards.

### 🔧 Powerful Bilingual Admin Panel
- **1-Click Bilingual Toggle**: Switch seamlessly between English and Simplified Chinese (`English` / `中文`).
- **Sockpuppet / Virtual User Generator**: Generate realistic synthetic user accounts & avatars to jumpstart community engagement.
- **Content Moderation**: Automated NSFW filtering, sensitive word blocklist, report handling, and user ban tools.
- **Dynamic Pricing Manager**: Modify model status, pricing, and multipliers on the fly without redeploying.

### 🌐 Creator Community & Social Ecosystem
- **Explore Gallery**: Responsive masonry layout with 1-click prompt copying and parameter inspection.
- **Creator Profiles**: Custom handles (`@username`), bios, avatars, and personal work showcases.
- **Social Engagement**: Likes, favorites, comments, and creator follows.
- **SEO Ready**: Auto-generated sitemaps, category aggregation (`/category/...`), and effect pages (`/effects/...`).

### ⚡ High-Performance Async Architecture
- **Celery Task Queues**: Heavy AI generation jobs run completely asynchronously without blocking API threads.
- **Real-Time WebSocket**: Instant job completion pushes directly to the frontend.

---

## ⚙️ Connect Real AI & Payments (Next Steps)

Ready to move from local testing to real AI generation? Simply fill in your API keys in `backend/.env` (or Docker environment variables):

```env
# 1. Real AI Providers (Setting a key automatically disables Mock mode)
REPLICATE_API_KEY="r8_your_replicate_api_key_here"
# GEMINI_API_KEY="your_gemini_api_key_here"

# 2. Payment Gateways (PayPal / Stripe)
PAYPAL_CLIENT_ID="your_paypal_client_id"
PAYPAL_CLIENT_SECRET="your_paypal_client_secret"
# STRIPE_SECRET_KEY="sk_live_..."

# 3. SMTP Email (For verification codes)
SMTP_HOST="smtp.example.com"
SMTP_PORT="465"
SMTP_USER="noreply@example.com"
SMTP_PASSWORD="your_smtp_password"

# 4. Google OAuth Login (Optional)
GOOGLE_CLIENT_ID="your_google_client_id"
GOOGLE_CLIENT_SECRET="your_google_client_secret"
```

---

## 🛠️ Tech Stack

| Component | Technologies |
| :--- | :--- |
| **Frontend Web** | **Nuxt 3.21.11** (Vue 3, SSR/ISR) + **Tailwind CSS** + **Pinia** + **Lucide Icons** |
| **Admin Panel** | **Nuxt 3.21.11** (Vue 3) + **Tailwind CSS** + Custom Bilingual i18n (EN/ZH) |
| **Backend API** | **FastAPI 0.141.1** (Python 3.11+) + **SQLAlchemy 2.0** + **Pydantic 2** |
| **Task Queue & Cache** | **Celery 5.4+** + **Redis 7** (Broker & Cache) + **Flower** (Queue Monitor) |
| **Database** | **PostgreSQL 15+** + **Alembic** Migrations |
| **Storage & CDN** | **Cloudflare R2** / AWS S3 / Aliyun OSS (S3-Compatible Object Storage) |
| **Deployment** | **Docker Compose** / **systemd** Automation Scripts / Nginx Reverse Proxy |

---

## 📚 Documentation

For manual development setup, architectural deep-dives, or production deployment guides, check out the documentation library:

- 🚀 **Getting Started**:
  - [Local Development Setup](docs/01-getting-started/local-development.md)
  - [Environment Variables Checklist](docs/01-getting-started/environment-variables.md)
- 🏗️ **Architecture & Systems**:
  - [System Architecture Overview](docs/02-architecture/system-overview.md)
  - [Workflow Engine & Node Execution](docs/02-architecture/workflow-engine.md)
  - [Credit Economics & Pricing Model](docs/02-architecture/credit-economics.md)
  - [Database Schema Dictionary](docs/03-subsystems/database-schema.md)
- 🔌 **Integrations**:
  - [Payment Gateways Integration (PayPal & Stripe)](docs/04-integrations/payment-gateways.md)
  - [Cloudflare R2 Storage Setup](docs/04-integrations/object-storage.md)
  - [AI Model Provider Extension Guide](docs/04-integrations/provider-extension-guide.md)
- 🚢 **Production Deployment**:
  - [Production Docker Guidelines](docs/05-deployment/docker-deployment.md)
  - [Linux systemd Deployment Guide](docs/05-deployment/production-deployment.md)

---

## 🔐 Production Docker Deployment

To deploy VidGen in production, use `docker-compose.prod.yml` with a private `.env.production` configuration:

```bash
# Generate strong secrets and credentials in .env.production, then run:
docker compose --env-file .env.production -f docker-compose.prod.yml up -d
```
> For complete production security baselines and TLS setup, see [Production Deployment Docs](docs/05-deployment/production-deployment.md).

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) — free for both personal and commercial use.

---

## 🤝 Contributing & Community

- Submit an [Issue](https://github.com/ucmao/vidgen/issues) to report bugs or request features.
- Pull Requests are always welcome!
- If VidGen helps you, please consider giving us a ⭐️ **Star** on GitHub!
