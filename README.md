# Home Ledger

Home Ledger is a household budget and expense tracking application for recording day-to-day transactions, organizing spending by custom categories/subcategories, and eventually managing monthly budgets with carryover.

The project is currently in the planning/setup phase. The first goal is a small MVP that tracks expense transactions by month and category hierarchy.

## Current Status

Planning/setup phase.

Start with the documentation index: [`docs/README.md`](docs/README.md)

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

- Add expense transactions manually.
- Store amount, date, description, and category/subcategory.
- List expense transactions by month.
- Show monthly expense totals.
- Show spending grouped by category and subcategory.

First vertical slice:

```text
Create expense transaction -> persist transaction -> display monthly transaction list
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

- [`docs/README.md`](docs/README.md) - documentation index
- [`docs/product-vision.md`](docs/product-vision.md) - long-term product direction
- [`docs/mvp.md`](docs/mvp.md) - current MVP scope
- [`docs/domain-model.md`](docs/domain-model.md) - core business concepts
- [`docs/roadmap.md`](docs/roadmap.md) - planned development phases
- [`docs/project-structure.md`](docs/project-structure.md) - repository and code organization
- [`docs/development-workflow.md`](docs/development-workflow.md) - issue, branch, and commit workflow
- [`docs/initial-plan.md`](docs/initial-plan.md) - original planning note

Additional docs may be added later:

```text
docs/api-design.md
docs/database-design.md
docs/decisions/
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
feature/transaction-api
feature/category-hierarchy
feature/monthly-summary
```

Example commits:

```text
feat: add transaction entity
feat: add expense transaction endpoint
fix: correct monthly total calculation
docs: update MVP scope
```

## Next Step

Set up the project skeleton:

- `backend/` Spring Boot project
- `frontend/` React + Vite project
- `docker-compose.yml` for PostgreSQL
- local run instructions
