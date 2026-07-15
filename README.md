# GAIA — Intelligent Academic Scheduling Manager

Intelligent Academic Scheduling Manager. A web-based platform that automates university scheduling using AI: it converts course catalogs, natural-language constraints, and faculty availability into complete, conflict-free schedules in minutes rather than weeks.

## Table of Contents

- [About this repository](#about-this-repository)
- [Project structure](#project-structure)
- [Tech stack](#tech-stack)
- [How to run the project](#how-to-run-the-project)
- [Configuration](#configuration)
- [Main features](#main-features)

---

## About this repository

This repository contains the full GAIA system: **backend** and **frontend** in a single monorepo. It manages faculty, courses, groups, classrooms, and generates full academic schedules, integrating AI to interpret natural-language constraints and free-text observations.

## Project structure

```
gaia/
├── backend/          # FastAPI service, database, AI integration
├── frontend/         # React + TypeScript client
├── docker-compose.yml
└── README.md
```

## Tech stack

**Backend**
- Python (FastAPI)
- PostgreSQL
- JWT authentication
- AI integration via Gemini / OpenRouter
- Docker

**Frontend**
- React + TypeScript + Vite
- Tailwind CSS

**Infrastructure**
- Docker & Docker Compose (containerized deployment, cloud-ready)

## How to run the project

### Requirements

- Docker
- Docker Compose

### Steps

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd gaia
   ```
2. Build and start all services:
   ```bash
   docker compose up --build
   ```
3. The backend and frontend will be running locally. The PostgreSQL database is started automatically as part of the Docker Compose setup — no manual configuration required.

## Configuration

The database is automatically provisioned with PostgreSQL through Docker. Environment variables (database credentials, JWT secret, AI provider API keys, etc.) should be set in a `.env` file — see `.env.example` in each service folder (not committed to the repository).

## Main features

- Academic management: programs, courses, faculty, groups, semesters, and day/night sessions
- AI-powered schedule generation from natural-language constraints (hard rules are validated; soft rules are best-effort)
- Bulk generation by group, program, faculty, or entire institution
- Visual calendar editor with real-time conflict validation
- Classroom assignment (regular rooms, labs, computer labs) by capacity and type
- Professional export to PDF and Excel, with automatic email delivery to faculty
- AI assistant for natural-language queries (schedules, conflicts, availability, room usage)
- Executive dashboard with metrics and charts (progress by program, load by day, top faculty)
