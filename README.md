📊 Personal Finance & Productivity Management System

A full-stack personal finance and productivity application that helps users track daily income/expenses, analyze weekly and monthly financial reports, manage multiple accounts, and plan daily tasks with postponement tracking.

The system is designed with real-world use cases in mind and follows clean architecture principles with a scalable backend, multi-client frontend, and DevOps-ready deployment.

✨ Key Features
💰 Finance Management

Track income and expenses by date, category, and account

Support multiple accounts (cash, bank, e-wallets)

Weekly and monthly financial summaries

Category-based expense breakdown

Period comparison (Week-over-Week, Month-over-Month)

📈 Reporting & Analytics

Total income, total expense, and net balance

Category distribution reports

Financial trend comparison across periods

Export reports to CSV / PDF

🗓 Productivity & Planning

Daily task planning (to-do list)

Task statuses: Pending, Done, Postponed

Track postponement history with reasons

Completion rate and productivity statistics

🧩 Dashboard (Web)

Manage accounts, categories, and budgets

View consolidated reports and analytics

Administrative insights and data management

🏗 System Architecture
┌─────────────────────────────── Clients ───────────────────────────────┐
│                                                                        │
│   ┌───────────────┐                         ┌──────────────────────┐  │
│   │ Flutter Mobile │                         │ React Web Dashboard  │  │
│   │ (User App)     │                         │ (Admin / Insights)   │  │
│   └───────┬───────┘                         └──────────┬───────────┘  │
│           │ HTTPS (REST / JSON)                         │ HTTPS        │
└───────────┴───────────────────────────┬─────────────────┴──────────────┘
                                        │
                                        ▼
                         ┌────────────────────────────────┐
                         │          Backend API            │
                         │        (NestJS Framework)       │
                         │                                │
                         │  - Authentication (JWT)         │
                         │  - Accounts & Categories         │
                         │  - Transactions                  │
                         │  - Reports & Comparisons         │
                         │  - Tasks & Postpone History      │
                         │  - Export Services               │
                         └───────────────┬────────────────┘
                                         │
                                         │ ORM (Prisma)
                                         ▼
                         ┌────────────────────────────────┐
                         │              MySQL              │
                         │  - users                         │
                         │  - accounts                      │
                         │  - categories                    │
                         │  - transactions                  │
                         │  - budgets (optional)            │
                         │  - tasks                         │
                         │  - task_postpone_history         │
                         └────────────────────────────────┘

🔄 Core Business Flow
Income / Expense Tracking
User → Create Transaction → API Validation → MySQL Storage
     → Aggregation Queries → Weekly/Monthly Reports → Charts & Insights

Task & Postponement Tracking
Create Task
   ├─ Mark as Done
   └─ Postpone Task → Log postponement reason & date → Update statistics

🗂 Data Model Overview (ERD)
users (1) ─── (N) accounts
users (1) ─── (N) transactions
accounts (1) ─── (N) transactions
categories (1) ─── (N) transactions

users (1) ─── (N) tasks
tasks (1) ─── (N) task_postpone_history

(Optional)
users (1) ─── (N) budgets
categories (1) ─── (N) budgets

🧰 Tech Stack
Backend

NestJS – Node.js framework for scalable server-side applications

Prisma ORM – Type-safe database access

MySQL – Relational database

JWT Authentication

Swagger / OpenAPI documentation

Frontend

ReactJS – Web dashboard

Flutter – Mobile application (Android/iOS)

DevOps

Docker & Docker Compose

GitHub Actions for CI/CD

Automated build, test, and deployment pipeline

🚀 CI/CD & Deployment Flow
git push
  │
  ├─> Lint & Test
  ├─> Build Docker Images
  ├─> Push to Container Registry
  └─> Deploy to VPS / Cloud Server

🧪 Local Development
docker-compose up -d


Services included:

Backend API

MySQL Database

Web Dashboard

📌 Project Goals

Apply real-world financial and productivity workflows

Demonstrate clean backend architecture

Support multi-platform clients

Practice DevOps & CI/CD automation

Build a production-ready portfolio project
