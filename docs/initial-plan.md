# Household Finance Tracker - Initial Plan

> This is the original planning document. Current planning has been split into focused documents for readability. Start with [`docs/README.md`](README.md) for the current documentation map.

---

## Purpose

Build a household expense tracker for day-to-day home expenses.

Primary goals:

- Track monthly spending.
- Track spending by category.
- Keep expense history searchable and easy to review.
- Add monthly/category budgets later.
- Use the project to practice realistic backend/full-stack development.

Keep the first version practical. No bank integrations, receipt scanning, mobile app, or complex auth until the core flow works.

---

## Stack

| Area | Choice | Notes |
|---|---|---|
| Backend | Java 21 + Spring Boot | Main professional-growth focus |
| API | REST | Simple and common for this app |
| Database | PostgreSQL | Relational DB, useful for reporting later |
| ORM | Spring Data JPA + Hibernate | CRUD, relationships, transactions |
| Frontend | React + TypeScript + Vite | Modern frontend stack, fast local dev |
| DB runtime | Docker Compose | Local PostgreSQL without manual setup |
| Planning | GitHub Issues + GitHub Projects | Backlog, milestones, feature tracking |
| Docs | Markdown in `/docs` | Keep decisions close to code |

Initial dev setup:

```text
PostgreSQL: Docker Compose
Backend: run locally
Frontend: run locally
```

---

## Architecture

```text
React frontend
  -> HTTP/JSON
Spring Boot REST API
  -> service layer
Spring Data JPA repositories
  -> Hibernate ORM
PostgreSQL
```

Main rule: keep business logic in the backend service layer, not in controllers or frontend components.

---

## Tooling Notes

### Docker

Use Docker Compose for local PostgreSQL.

Why:

- Avoid manual PostgreSQL setup on Windows.
- Keep DB version/config repeatable.
- Make future setup easier on another machine.
- Practice a common professional workflow.

Do not containerize everything at the start. Start with DB only.

### ORM / JPA / Hibernate

Use JPA entities for core tables like `Expense`, `Category`, `HouseholdMember`, and later `Budget`.

Use ORM for:

- Basic CRUD.
- Entity relationships.
- Transaction management.

Use custom queries when needed for:

- Monthly summaries.
- Spending by category.
- Reports/analytics.

---

## MVP Scope

The first useful version should support:

- Add expenses manually.
- Store amount, date, description, and category.
- View expenses for a selected month.
- Show total monthly spending.
- Show spending by category.

First vertical slice:

```text
Add expense -> save to DB -> list expenses in UI
```

Do this before dashboards, budgets, auth, or charts.

---

## Core Domain Model - Draft

Initial concepts:

```text
Household
HouseholdMember
Expense
Category
Budget       later
```

`Expense` draft fields:

```text
id
amount
date
description
category
createdAt
updatedAt
```

`Budget` draft fields, for later:

```text
id
month
year
category
limitAmount
```

Budget remaining should be calculated from expenses, not manually stored at first.

---

## Roadmap

### MVP

- Project structure.
- PostgreSQL via Docker Compose.
- Spring Boot backend.
- React frontend.
- Expense CRUD.
- Categories.
- Monthly summary.

### v0.2 - Budgets

- Monthly/category budgets.
- Budget remaining view.
- Budget warning states.

### v0.3 - Reports

- Charts.
- Category trends.
- Month-over-month comparison.
- CSV export/import.

### v0.4 - Real App Features

- Authentication.
- Household/member management.
- Deployment.
- Backups.

---

## Repository Shape

```text
home-ledger/
  backend/
  frontend/
  docs/
    initial-plan.md
  docker-compose.yml
  README.md
```

Add more docs only when useful:

```text
docs/domain-model.md
docs/api-design.md
docs/database-design.md
docs/roadmap.md
```

---

## GitHub Project Setup

Board columns:

```text
Backlog -> Ready -> In Progress -> Done
```

Labels:

```text
backend
frontend
database
docs
feature
bug
refactor
learning
```

Milestones:

```text
MVP
v0.2 Budgets
v0.3 Reports
v0.4 Auth + Deploy
```

---

## First Issues

Setup:

- Create repo structure.
- Add Docker Compose for PostgreSQL.
- Generate Spring Boot backend.
- Generate React/Vite frontend.
- Add root README.

Backend MVP:

- Configure backend DB connection.
- Add initial Flyway migration.
- Create `Expense` entity.
- Create `Category` entity.
- Create `HouseholdMember` entity.
- Add expense create/list endpoints.
- Add monthly summary endpoint.

Frontend MVP:

- Basic app layout.
- Expense form.
- Expense list.
- Month selector.
- Monthly summary view.

---

## Development Workflow

For each feature:

1. Create/choose a GitHub issue.
2. Create a branch.
3. Implement backend/domain logic first when relevant.
4. Add basic tests for business logic.
5. Add frontend UI.
6. Update docs if a decision changed.
7. Merge to `main`.

Branch examples:

```text
feature/expense-api
feature/expense-form
feature/monthly-summary
```

Commit examples:

```text
feat: add expense entity
feat: add expense creation endpoint
fix: correct monthly total calculation
docs: update MVP scope
```

---

## Next Step

Set up the project skeleton:

```text
backend/ Spring Boot
frontend/ React + Vite
docker-compose.yml for PostgreSQL
README.md with local run instructions
```

Then build the first vertical slice:

```text
Create expense -> persist expense -> display expense list
```