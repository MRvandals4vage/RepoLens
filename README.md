# 🔍 RepoLens

**Understand any codebase in minutes.**

RepoLens is an AI-powered, comprehensive repository analysis and visualization tool. It automatically scans repositories, detects frameworks, builds architectural mental models, and provides a clear, interactive visual structure of the codebase. Instead of spending days reading through undocumented source code, RepoLens gives you the architect's view instantly.

---

## ✨ Features

- **Automated Repository Intelligence**: Feed it a GitHub URL or a ZIP file, and it analyzes it in seconds.
- **AI Architect (Groq Integration)**: Powered by Llama 3 on Groq, RepoLens synthesizes an onboarding guide to walk you through the codebase, modular structure, and critical execution paths.
- **Architecture & Dependency Flow**: Auto-generates Mermaid charts that visualize conceptual system architectures and infrastructure/module dependencies.
- **Framework & Language Detection**: Automatically identifies frameworks (e.g., Next.js, React, Node.js, Spring Boot, Actix) and languages within the repository using AST-based scanning.
- **Glassmorphic UI**: A premium, modern interface featuring a stunning deep black, emerald green, and celery color palette with smooth animations and ambient glow accents.
- **Execution Flow & Risk Hotspots**: Outlines the runtime path using entrypoints and discovers structural risks (e.g., highly coupled dependency hubs).
- **Export Docs**: Easily export the entire analysis, including AI explanations, as a Markdown document for easy offline sharing.
- **Dockerized Foundation**: Fully containerized setup for seamless deployment and local testing.

---

## 🏗️ Architecture

RepoLens is split into two primary services:

- **Frontend**: A Next.js web application styled with Tailwind CSS, providing a dynamic glassmorphic interface and interactive visualizations.
- **Backend**: An Express.js Node backend that utilizes `simple-git`, `tree-sitter`, and the `Groq SDK` to handle AST-based semantic analysis, language parsing, file-tree generation, and LLM reasoning.

---

## 🚀 Getting Started

The easiest way to run RepoLens is with Docker Compose. Node.js 20+ is the standard runtime.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) & [Docker Compose](https://docs.docker.com/compose/install/)
- A [Groq API Key](https://console.groq.com/keys) (required for AI architectural reasoning)

### 1. Clone the Repository

```bash
git clone https://github.com/MRvandals4vage/RepoLens.git
cd RepoLens
```

### 2. Configure Environment Variables

Create a `.env` file in the root directory and add your Groq API key to power the AI features:

```env
# .env
GROQ_API_KEY=gsk_your_api_key_here
GROQ_MODEL=llama-3.3-70b-versatile
BACKEND_PORT=5001
FRONTEND_PORT=3000
NEXT_PUBLIC_API_URL=http://localhost:5001
```

### 3. Run with Docker Compose

```bash
docker compose up --build -d
```

### 4. Explore

Open your browser and navigate to `http://localhost:3000` to access the RepoLens interface! 
The backend API runs concurrently on `http://localhost:5001`.

---

## 🎨 Design

RepoLens was designed with best-in-class UI/UX principles to make exploring dense codebases enjoyable. The dynamic theme relies on:
- Dark void backgrounds (`#000000` to `#141414`).
- Emerald and Celery glowing interactables (`#10b981`, `#b8c25d`).
- Clean typography utilizing Next.js `Geist` and `Geist Mono` fonts.

---

## 📜 License
ISC License
