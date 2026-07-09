# Home Ledger

Household expense tracker for day-to-day home expenses.

The goal is to track monthly expenses, understand spending by category, and eventually manage monthly/category budgets.

## Current Status

Planning/setup phase.

Initial project plan: [`docs/initial-plan.md`](docs/initial-plan.md)

## Planned Stack

| Area | Tech |
|---|---|
| Backend | Java 21, Spring Boot |
| API | REST |
| Database | PostgreSQL |
| ORM | Spring Data JPA, Hibernate |
| Frontend | React, TypeScript, Vite |
| Local services | Docker Compose |
| Planning | GitHub Issues, GitHub Projects |

## Planned Repository Structure

```text
home-ledger/
  backend/
  frontend/
  docs/
  docker-compose.yml
  README.md
```

## MVP

First useful version:

- Add expenses manually.
- Store amount, date, description, and category.
- List expenses by month.
- Show monthly totals.
- Show spending by category.

First vertical slice:

```text
Create expense -> persist expense -> display expense list
```

## Local Development

Detailed setup will be added once the backend, frontend, and Docker Compose files exist.

Expected workflow:

```text
1. Start PostgreSQL with Docker Compose.
2. Run the Spring Boot backend locally.
3. Run the React/Vite frontend locally.
```

## Documentation

- [`docs/initial-plan.md`](docs/initial-plan.md) - initial product and technical plan

Additional docs may be added later:

```text
docs/domain-model.md
docs/api-design.md
docs/database-design.md
docs/roadmap.md
```

## Development Workflow

For each feature:

1. Create or choose a GitHub issue.
2. Create a feature branch.
3. Implement backend/domain logic first when relevant.
4. Add basic tests for business logic.
5. Add frontend UI.
6. Update docs if a decision changed.
7. Merge to `main`.

Example branches:

```text
feature/expense-api
feature/expense-form
feature/monthly-summary
```

Example commits:

```text
feat: add expense entity
feat: add expense creation endpoint
fix: correct monthly total calculation
docs: update MVP scope
```

## Next Step

Set up the project skeleton:

- `backend/` Spring Boot project
- `frontend/` React + Vite project
- `docker-compose.yml` for PostgreSQL
- local run instructions
