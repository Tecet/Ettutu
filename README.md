# Ettutu V2 🚀

## Currently in Beta testing stage. 

## Video Presentaion:
https://youtu.be/4o_OW4o0CgA?si=g6eggfdjHhyZHwnI

## Introduction 
**Next-generation lead harvesting platform with modular plugin architecture**

Ettutu V2 is a lead harvesting and contact management platform that helps teams find, analyze, and manage business leads more efficiently.

**Non-Technical Preview**

- **What it is:** A tool that finds business contacts (emails, phone numbers, websites), scores and organizes them, and makes exporting to CRMs and spreadsheets easy.
- **Who it's for:** Small sales teams, marketing operators, and growth teams who need a tidy way to discover and manage potential customers without manual research.
- **Why it helps:** Saves time by automating data collection, summarizes the most useful information about a lead, and integrates with common workflows so teams can act faster.
- **Try it:** There is a demo environment included for safe experimentation—see the docs/Non-Technical-Preview.md file for quick steps.

- 🧩 **Plugin-First Architecture** - Every tool (crawler, analyzer, exporter) is a self-contained plugin
- 🗄️ **Data-Centric Design** - Full CRUD database with advanced search, not just a viewer
- 🔌 **Modular System** - Remove any component without breaking the app
- 🌐 **Universal Deployment** - Same codebase runs locally and in production

---

## Features

### Core Capabilities

- ✅ Google Places search with multi-account support
- ✅ Website crawling (Fast/Deep/LLM strategies)
- ✅ LLM-powered analysis (CLI Bridge, Ollama, API providers)
- ✅ CRM export (Twenty CRM, CSV)
- ✅ Pipeline management (Kanban-style leads)
- ✅ Full-text search across records
- ✅ Async job queue with progress tracking

### Plugin System

- **Crawlers**: Fast (regex), Deep (multi-page), LLM (dynamic schema)
- **Analyzers**: Lead Scorer, Industry Classifier
- **Exporters**: Twenty CRM, CSV, JSON
- **Importers**: CSV with column mapping

---

## Tech Stack

| Layer        | Technology                        |
| ------------ | --------------------------------- |
| **Frontend** | React 18 + Vite + TypeScript      |
| **Backend**  | Python 3.12 + FastAPI             |
| **Database** | PostgreSQL 16 (self-hosted)       |
| **ORM**      | SQLAlchemy 2.0 (async)            |
| **Queue**    | SAQ (Simple Async Queue)          |
| **Crawling** | Crawl4AI + Playwright             |
| **LLM**      | CLI Bridge, Ollama, API providers |
| **Infra**    | Docker Compose + Traefik-ready    |

---

## Quick Start

### Prerequisites

- Docker & Docker Compose
- **Nvidia Container Toolkit** (for local LLM/Ollama GPU support) - _Optional but Recommended_
  - [Installation Guide](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
  - **Windows Users:** Ensure Docker Desktop is using the WSL 2 backend.
- Python 3.12+ (for local development)
- Node.js 20+ (for frontend development)





## Project Structure

```
ettutu-v2/
├── backend/                 # FastAPI backend
│   ├── src/
│   │   ├── api/            # API routes
│   │   ├── core/           # Core systems (plugins, LLM)
│   │   ├── db/             # Database models
│   │   ├── plugins/        # Plugin implementations
│   │   ├── workers/        # Background jobs
│   │   └── services/       # Business logic
│   ├── alembic/            # Database migrations
│   └── requirements.txt
│
├── frontend/                # React frontend
│   ├── src/
│   │   ├── api/            # API client
│   │   ├── components/     # React components
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom hooks
│   │   └── stores/         # State management
│   └── package.json
│
└── docker-compose.yml       # Docker orchestration
```

---


## Contributing

Contributions are welcome! Please read the [development plan](./ettutu-v2-development-plan.md) first to understand the architecture.

---

## Support

For issues and questions, please open a GitHub issue.
