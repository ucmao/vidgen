<div align="center">

<img src="docs/assets/logo.png" alt="VidGen Logo" width="320" style="border-radius: 20px; box-shadow: 0 4px 20px rgba(0,0,0,0.15);" />

<p><b>开箱即用、高性能的全栈开源 AI 视频与图像生成平台</b></p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Nuxt 3](https://img.shields.io/badge/Nuxt-3.21.11-00DC82?style=for-the-badge&logo=nuxt.js&logoColor=white)](https://nuxt.com/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.141.1-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Docker Compose](https://img.shields.io/badge/Docker%20Compose-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](docker-compose.yml)

[English](README.md) | [简体中文](README_CN.md)

</div>

<p align="center">
  <a href="https://vidgenerator.ai"><b>🚀 在线演示</b></a> •
  <a href="#-1-分钟极速上手-docker"><b>⚡ 极速体验</b></a> •
  <a href="#-核心特性"><b>✨ 核心特性</b></a> •
  <a href="#️-接入真实-ai-与支付"><b>⚙️ 商业化配置</b></a> •
  <a href="#-完整文档"><b>📚 开发文档</b></a>
</p>

---

> 🚀 **真实生产验证（Battle-Tested）**：VidGen 为真实线上商业运营项目 [vidgenerator.ai](https://vidgenerator.ai) 提供核心系统支持。

## 🌟 什么是 VidGen？

**VidGen** 是一套专为创作者、独立开发者和创业者打造的开源 AI 视频与图像生成系统。

无论你是想在 **5 分钟内**自建一个类似 Midjourney / Luma 的 AI 生成网站，还是打造专属的 AI 商业化产品，VidGen 都能提供**全链路闭环解决方案**：从现代化 Nuxt 3 用户门户、中英双语管理后台、Celery 异步生成引擎，到**积分变现、在线支付、社区广场、虚拟马甲与内容审核**，全部开箱即用！

---

## ⚡ 1 分钟极速上手 (Docker)

无需配置复杂的 Python/Node 环境，无需搭建数据库，甚至**无需申请任何付费 API Key**（默认开启 Mock 模式与演示数据，0 成本本地试玩），一条命令即可完整启动！

### 1. 克隆并启动

```bash
# 1. 克隆项目
git clone https://github.com/ucmao/vidgen.git
cd vidgen

# 2. 一键启动全套 6 个服务 (Web 前端、Admin 后台、FastAPI、Celery 队列、PostgreSQL、Redis)
docker compose up -d
```

### 2. 立即访问

服务启动后，在浏览器中打开即可直接使用：

| 服务 | 访问地址 | 默认账号 / 说明 |
| :--- | :--- | :--- |
| 🌐 **用户端前台** | `http://localhost:3000` | 已预装演示数据与 Mock 生成引擎，直接体验 |
| 🔧 **管理后台 (Admin)** | `http://localhost:3001` | 用户名：`admin`（密码见首次启动终端日志，或配置 `INITIAL_ADMIN_PASSWORD`） |
| 🐍 **API 交互文档** | `http://localhost:8000/docs` | Swagger 交互式接口文档与调试 |

> 💡 **小白贴士**：
> - 想要查看运行状态与实时日志？运行 `docker compose logs -f backend`。
> - 容器首次启动会自动执行数据迁移并生成演示数据，开箱即可体验全部前后台功能。

---

## ✨ 核心特性

### 🎨 多模态 AI 生成
- **文生图 (Text-to-Image)**：支持 FLUX.1、SDXL、Midjourney 等先进模型，一键生成高清图片。
- **图生图 (Image-to-Image)**：支持参考图垫图与 Prompt 引导，实现风格重绘与细节微调。
- **文生视频 (Text-to-Video)**：支持 HunyuanVideo、Luma、Pika、Runway 等动态视频生成。
- **图生视频 (Image-to-Video)**：让静态照片动起来，支持运动幅度与画面动态调节。

### 💰 商业化与支付闭环
- **全球主流支付**：原生集成 **PayPal** 与 **Stripe** 支付网关，支持订阅与积分充值。
- **按量积分计费**：支持为不同模型、清晰度、步骤灵活配置积分消耗。
- **运营促销体系**：支持折扣优惠券、限时促销包、每日签到阶梯奖励。

### 🔧 强大的中英文管理后台
- **双语极速切换**：纯英文/中文界面顶栏一键切换 (`English` / `中文`)。
- **马甲账号生成器**：一键批量生成高真实感虚拟用户与作品，快速冷启动社区。
- **内容安全审核**：集成敏感词库、NSFW 智能检测、用户举报处理与一键封禁。
- **可视化模型定价**：后台直接管理模型状态、基础价格与加价规则，无需重启服务。

### 🌐 社区广场与社交生态
- **探索画廊**：瀑布流作品展示，一键复制 Prompt 提示词与模型参数。
- **创作者主页**：自定义个人主页、Handle 域名 (`@username`)、头像与作品集。
- **社交互动**：支持点赞、收藏、作品评论与关注作者。
- **深度 SEO**：自动生成 Sitemap、分类聚合页 (`/category/...`)、特效聚合页 (`/effects/...`)。

### ⚡ 高性能异步架构
- **Celery 异步任务队列**：图片/视频渲染完全解耦异步化，高并发下依然丝滑流畅。
- **WebSocket 实时推送**：任务完成后秒级推送通知前端，体验极佳。

---

## ⚙️ 接入真实 AI 与支付（进阶配置）

当你想从“本地试玩”转为“真实使用”时，只需在 `backend/.env`（或 Docker 环境变量）中填入对应 Key 即可：

```env
# 1. 接入真实 AI 服务商（填入后将自动关闭 Mock 模式）
REPLICATE_API_KEY="r8_your_replicate_api_key_here"
# GEMINI_API_KEY="your_gemini_api_key_here"

# 2. 接入支付（支持 PayPal / Stripe）
PAYPAL_CLIENT_ID="your_paypal_client_id"
PAYPAL_CLIENT_SECRET="your_paypal_client_secret"
# STRIPE_SECRET_KEY="sk_live_..."

# 3. 邮件服务（用于用户注册邮箱验证码）
SMTP_HOST="smtp.example.com"
SMTP_PORT="465"
SMTP_USER="noreply@example.com"
SMTP_PASSWORD="your_smtp_password"

# 4. Google 一键快捷登录（可选）
GOOGLE_CLIENT_ID="your_google_client_id"
GOOGLE_CLIENT_SECRET="your_google_client_secret"
```

---

## 🛠️ 技术栈一览

| 模块 | 核心技术选型 |
| :--- | :--- |
| **前端 Web 门户** | **Nuxt 3.21.11** (Vue 3, SSR/ISR) + **Tailwind CSS** + **Pinia** + **Lucide Icons** |
| **管理后台 Admin** | **Nuxt 3.21.11** (Vue 3) + **Tailwind CSS** + 自定义 i18n 中英双语 |
| **后端 API 服务** | **FastAPI 0.141.1** (Python 3.11+) + **SQLAlchemy 2.0** + **Pydantic 2** |
| **异步队列与缓存** | **Celery 5.4+** + **Redis 7** (Broker & Cache) + **Flower** (队列监控) |
| **数据库** | **PostgreSQL 15+** + **Alembic** 数据库迁移管理 |
| **对象存储 & CDN** | **Cloudflare R2** / AWS S3 / 阿里云 OSS (兼容 S3 协议) |
| **部署与容器化** | **Docker Compose** / **systemd** 自动化运维脚本 / Nginx 反向代理 |

---

## 📚 完整开发与部署文档

想要深入定制或进行生产环境部署？请查阅我们的详细文档库：

- 🚀 **快速上手**：
  - [本地开发环境搭建指南](docs/01-getting-started/local-development.md)
  - [环境变量完整配置清单](docs/01-getting-started/environment-variables.md)
- 🏗️ **架构与系统**：
  - [系统架构与全景图](docs/02-architecture/system-overview.md)
  - [工作流引擎与节点设计](docs/02-architecture/workflow-engine.md)
  - [积分经济与定价模型](docs/02-architecture/credit-economics.md)
  - [数据库 Schema 字典](docs/03-subsystems/database-schema.md)
- 🔌 **第三方集成**：
  - [支付网关接入指南 (PayPal & Stripe)](docs/04-integrations/payment-gateways.md)
  - [Cloudflare R2 存储配置](docs/04-integrations/object-storage.md)
  - [AI 模型 Provider 扩展教程](docs/04-integrations/provider-extension-guide.md)
- 🚢 **生产部署与运维**：
  - [生产环境 Docker 部署标准](docs/05-deployment/docker-deployment.md)
  - [Linux systemd 生产部署指南](docs/05-deployment/production-deployment.md)

---

## 🔐 生产环境 Docker 快速部署

若将 VidGen 部署于生产服务器，请使用 `docker-compose.prod.yml` 并准备独立的 `.env.production` 环境变量：

```bash
# 生成高强度密码与密钥并写入 .env.production 后运行：
docker compose --env-file .env.production -f docker-compose.prod.yml up -d
```
> 详细生产安全与 Nginx TLS 配置，请阅读 [生产部署文档](docs/05-deployment/production-deployment.md)。

---

## 📄 开源许可证

本项目基于 [MIT License](LICENSE) 协议开源，允许自由用于个人研究及商业用途。

---

## 🤝 贡献与支持

- 欢迎提交 [Issue](https://github.com/ucmao/vidgen/issues) 反馈 Bug 或提出功能建议。
- 欢迎提交 Pull Request 共同完善项目！
- 如果 VidGen 对您的项目有所帮助，欢迎在 GitHub 上点个 ⭐️ **Star** 支持作者！
