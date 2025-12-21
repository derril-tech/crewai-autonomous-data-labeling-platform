# 🚀 Autonomous Data Labeling Platform
**AI-Powered Human-in-the-Loop Labeling with Active Learning**

🌐 **[View Live Application](https://crewai-autonomous-data-labeling-pla.vercel.app)**

> **Accelerate your ML data pipeline. Let AI pre-label text, images, and audio with confidence scores, then verify in a keyboard-first workspace designed for speed. Continuous improvement through active learning ensures your models get better over time.** ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black.svg)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.2-61DAFB.svg)](https://react.dev/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-009688.svg)](https://fastapi.tiangolo.com/)
[![Railway](https://img.shields.io/badge/Deploy-Railway-blueviolet.svg)](https://railway.app/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black.svg)](https://vercel.com/)

---

## ✨ What It Does

This platform orchestrates the complete data labeling workflow—from raw data to production-ready labeled datasets. It combines **ML operations**, **data quality assurance**, and **human-in-the-loop UX** to deliver:

1. **AI Pre-labeling** — GPT-4.1-mini generates draft annotations with confidence scores using structured outputs
2. **Smart Verification** — Keyboard-first workspace optimized for rapid human review and correction
3. **Active Learning** — Intelligent queue prioritization surfaces items needing attention (low confidence, conflicts)
4. **Quality Assurance** — Automated conflict detection, drift monitoring, and quality metrics
5. **Continuous Improvement** — Active learning loop refines model suggestions based on human feedback

All orchestrated through a modern, responsive interface that works seamlessly on desktop and mobile.

---

## 🎯 Core Features

### 🤖 **AI-Powered Pre-labeling**
- **OpenAI Integration** — GPT-4.1-mini with structured JSON outputs for reliable parsing
- **Confidence Scoring** — 0.0-1.0 scale with detailed thresholds for quality assessment
- **Multi-Modality Support** — Text classification, image bounding boxes, audio segments
- **CrewAI Orchestration** — Multi-agent workflow for pre-labeling, QA, and guidance
- **Rate Limiting & Caching** — Efficient API usage with intelligent result caching

### 📊 **Data Quality & Analytics**
- **Real-time Analytics Dashboard** — KPIs, trend charts, and quality insights
- **Conflict Detection** — AI-powered QA flags inconsistencies and drift
- **Quality Metrics** — Verified rates, confidence distributions, edit rates
- **Activity Timeline** — Complete audit trail of labeling actions
- **Smart Search** — AI-powered semantic search across items and annotations

### ⚡ **Keyboard-First Labeling Workspace**
- **Lightning-Fast Navigation** — J/K for next/prev, A to approve, S to save
- **Bulk Operations** — Approve, reject, or set class for multiple items at once
- **Context-Aware Hints** — AI explains why labels were suggested with similar examples
- **Queue Filters** — Focus on items needing review, verified, or draft
- **Mobile-Optimized** — Responsive layout with collapsible panels for touch devices

### 🎨 **Modern UI/UX**
- **React 19.2 Features** — Server Components, Suspense, `use()` hook, optimistic updates
- **Dark/Light Mode** — Beautiful theme with system preference support
- **Mobile-First Design** — 44px+ touch targets, responsive grids, bottom navigation
- **Real-time Updates** — Live job progress, instant annotation sync
- **Accessibility** — WCAG AA contrast, keyboard navigation, focus states

### 📱 **Complete Feature Set**

| Feature | Description |
|---------|-------------|
| 🗂️ **Dataset Management** | Create and manage text/image/audio datasets |
| 📝 **Schema Definition** | Versioned labelsets with JSON schema validation |
| 🤖 **AI Pre-labeling** | Automated draft annotations with confidence scores |
| ✅ **Human Verification** | Fast keyboard-first workspace for review |
| 📊 **Analytics Dashboard** | Real-time KPIs, trends, and quality insights |
| 💬 **AI Chat Assistant** | Interactive assistant for labeling guidance |
| 🔍 **Smart Search** | Semantic search across items and annotations |
| ⚡ **Active Learning Queue** | Prioritized items based on uncertainty scores |
| 🔄 **Bulk Operations** | Approve/reject/set class for multiple items |
| 🚨 **QA Conflict Detection** | Automated flagging of inconsistencies |
| 📈 **Quality Metrics** | Verified rates, confidence, drift tracking |
| 👥 **Collaboration** | Annotation history and activity tracking |
| 📤 **Export Formats** | JSONL, COCO-lite, CSV export options |
| 📱 **Mobile Support** | Full-featured mobile experience |

---

## 🏗️ Tech Stack

### **Frontend** ⚛️
| Technology | Purpose |
|------------|---------|
| **Next.js 16.0.10** | React 19.2 with App Router, Server Components |
| **TypeScript** | Type-safe development with shared types |
| **Tailwind CSS** | Utility-first styling with semantic tokens |
| **shadcn/ui** | Accessible component library |
| **Recharts** | Data visualization for analytics |
| **Lucide Icons** | Modern icon set |

### **Backend** 🐍
| Technology | Purpose |
|------------|---------|
| **FastAPI** | High-performance async Python API |
| **Pydantic v2** | Data validation and serialization |
| **OpenAI SDK** | GPT-4.1-mini with structured outputs |
| **CrewAI** | Multi-agent orchestration for labeling workflows |
| **Uvicorn** | ASGI server with async support |

### **Data & Infrastructure** 💾
| Technology | Purpose |
|------------|---------|
| **Supabase PostgreSQL** | Primary database with private schema architecture |
| **pgvector** | Vector embeddings for similarity search (Supabase extension) |
| **Upstash Redis** | Job queue, caching, rate limiting |
| **Supabase Storage** | Asset storage with signed URLs (images/audio) |

### **Deployment** 🚀
| Platform | Service |
|----------|---------|
| **Vercel** | Frontend hosting (Next.js) |
| **Railway** | Backend API (FastAPI) |

---

## 🔄 How It Works

```
┌─────────────────────────────────────────────────────────────┐
│                    DATA INGESTION                            │
│         Upload text/images/audio → Create dataset            │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                 SCHEMA DEFINITION                            │
│         Define labelset (classes, modality, config)         │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              AI PRE-LABELING (OpenAI + CrewAI)              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Prelabel   │  │     QA       │  │  Guidance    │      │
│  │   Agent      │──│   Agent      │──│   Agent      │      │
│  │  (OpenAI)    │  │  (Conflict)  │  │  (Hints)     │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
│         │                  │                  │            │
│         └──────────────────┴──────────────────┘            │
│                    Draft Annotations                        │
│              (with confidence scores)                       │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│            HUMAN VERIFICATION WORKSPACE                      │
│  • Keyboard-first navigation (J/K/A/S)                       │
│  • AI hints panel with rationale                             │
│  • Bulk operations for efficiency                            │
│  • Active learning queue prioritization                      │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              QUALITY ASSURANCE & ANALYTICS                  │
│  • Conflict detection and flagging                           │
│  • Quality metrics (verified rate, confidence, drift)        │
│  • Real-time dashboard with trends                           │
│  • Activity timeline and audit trail                         │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                    EXPORT & DEPLOY                           │
│  • JSONL, COCO-lite, CSV formats                             │
│  • Verified annotations ready for training                   │
│  • Active learning feedback loop                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 📖 User Guide

### Getting Started

1. **Create Dataset** — Navigate to Datasets, enter name and select modality (text/image/audio)
2. **Add Items** — Paste text items or upload files (images/audio)
3. **Define Schema** — Create labelset with classes and configuration
4. **Run Pre-labeling** — AI generates draft annotations with confidence scores
5. **Verify Labels** — Use keyboard-first workspace to review and approve
6. **Export** — Download verified annotations in JSONL format

### Understanding Quality Metrics

| Metric | What It Means |
|--------|---------------|
| **Verified Rate** | Percentage of items with verified annotations |
| **Confidence Score** | AI's certainty (0.0-1.0) — lower = needs review |
| **Active Score** | Prioritization score for active learning queue |
| **Drift Score** | Measure of annotation consistency over time |
| **Conflict Count** | Number of QA-flagged inconsistencies |

---

## 🏗️ Architecture Highlights

### **ML Operations**
- **Structured AI Outputs** — JSON schema validation ensures reliable parsing
- **Confidence Calibration** — Detailed scoring guidelines for accurate uncertainty estimation
- **Active Learning** — Heuristic-based prioritization surfaces high-value items
- **Vector Search** — pgvector for finding similar examples to guide labeling

### **Data Quality**
- **Multi-Layer Validation** — Schema validation, payload validation, QA conflict detection
- **Audit Trail** — Complete history of annotation changes and reviews
- **Quality Metrics** — Real-time tracking of verified rates, confidence distributions, drift
- **Export Validation** — Ensures exported data meets format requirements

### **Human-in-the-Loop UX**
- **Keyboard-First Design** — Optimized for rapid labeling workflows
- **Context-Aware Hints** — AI explains suggestions with similar examples
- **Bulk Operations** — Efficient batch processing for large datasets
- **Mobile Support** — Full-featured experience on touch devices

### **Production-Ready Infrastructure**
- **Private Schema Architecture** — Secure database access via RPC functions
- **Async/Await Throughout** — Non-blocking I/O for scalability
- **Rate Limiting** — Protects API from abuse
- **Error Handling** — Graceful fallbacks and user-friendly error messages

---

## 📊 Performance & Quality

| Metric | Value |
|--------|-------|
| **Pre-labeling Speed** | ~1-2 seconds per item (with caching) |
| **Labeling Workspace** | <100ms navigation between items |
| **Mobile Responsiveness** | Fully optimized (6.5/10 → 9/10 after fixes) |
| **API Response Time** | <200ms average (p95) |
| **Database Queries** | Optimized with indexes and RPC functions |

---

## 🎨 Design Philosophy

This platform demonstrates production-grade engineering across multiple domains:

### **ML Operations Excellence**
- Structured AI outputs with validation
- Confidence calibration and uncertainty quantification
- Active learning for efficient human effort allocation
- Vector similarity search for context-aware guidance

### **Data Quality Engineering**
- Multi-layer validation (schema, payload, QA)
- Real-time quality metrics and drift detection
- Complete audit trail for compliance
- Export format validation

### **Human-Centered UX**
- Keyboard-first design for power users
- Context-aware AI hints with similar examples
- Bulk operations for scale
- Mobile-optimized for on-the-go labeling

### **Production Infrastructure**
- Private schema architecture for security
- Async/await throughout for scalability
- Rate limiting and error handling
- Comprehensive monitoring and analytics

---

## 🛡️ Security & Privacy

- ✅ **Private Schema** — Database access via RPC functions, schema not exposed
- ✅ **Signed URLs** — Secure asset uploads/downloads with expiration
- ✅ **API Rate Limiting** — Protects against abuse (60 req/min prelabel, 30 req/min hints)
- ✅ **Input Validation** — Pydantic models validate all inputs
- ✅ **CORS Protection** — Configured for specific origins
- ✅ **Environment Variables** — All secrets stored securely

---

## 📸 Key Screenshots

### 🏠 Landing Page
*Modern hero section with video background and clear value proposition*

### 📊 Dashboard
*Real-time analytics with KPIs, trend charts, and activity feed*

### 🎯 Labeling Workspace
*Keyboard-first interface with AI hints, queue navigation, and bulk operations*

### 💬 AI Chat Assistant
*Interactive assistant for labeling guidance and workflow questions*

### 📱 Mobile Experience
*Fully responsive design with collapsible panels and touch-optimized controls*

---

## 👨‍💻 Creator

**Derril Filemon**

This project showcases expertise in:

- 🤖 **ML Operations** — AI integration, structured outputs, active learning, vector search
- 📊 **Data Quality** — Validation pipelines, QA systems, quality metrics, audit trails
- ⚛️ **Modern Frontend** — Next.js 16, React 19.2, Server Components, TypeScript
- 🐍 **Python Backend** — FastAPI, async/await, Pydantic, database architecture
- 🎨 **UX Design** — Keyboard-first workflows, mobile optimization, accessibility
- ☁️ **Cloud Infrastructure** — Supabase, Redis, Railway, Vercel, production deployment
- 🔧 **DevOps** — CI/CD, environment management, monitoring, testing

---

## 🙏 Acknowledgments

- **[OpenAI](https://openai.com/)** — GPT-4.1-mini API with structured outputs
- **[CrewAI](https://www.crewai.com/)** — Multi-agent orchestration framework
- **[Supabase](https://supabase.com/)** — PostgreSQL, Storage, and pgvector
- **[Upstash](https://upstash.com/)** — Serverless Redis
- **[Railway](https://railway.app/)** — Backend deployment platform
- **[Vercel](https://vercel.com/)** — Frontend hosting
- **[shadcn/ui](https://ui.shadcn.com/)** — Beautiful, accessible components
- **[Next.js](https://nextjs.org/)** — React framework
- **[Recharts](https://recharts.org/)** — Data visualization

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

[Live Demo](https://crewai-autonomous-data-labeling-pla.vercel.app) 

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

**AI Engineer & Fullstack Developer** • Göteborg, Sweden

</div>
