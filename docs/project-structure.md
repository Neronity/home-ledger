# Project Structure

Home Ledger uses a small monorepo structure.

The frontend and backend live in the same Git repository, but they are separate applications.

## Root Structure

```text
home-ledger/
  backend/              Spring Boot REST API
  frontend/             React/Vite web app
  docs/                 project documentation
  docker-compose.yml    local PostgreSQL runtime
  README.md             project entrypoint
```

## Local Runtime Model

During development, run three pieces:

```text
PostgreSQL database  localhost:5432
Spring Boot backend  localhost:8080
React/Vite frontend  localhost:5173
```

Request flow:

```text
Browser
  -> React frontend
    -> Spring Boot REST API
      -> PostgreSQL
```

## Backend Organization

Use feature-oriented packages instead of one global package per technical layer.

Planned shape:

```text
backend/src/main/java/.../homeledger/
  HomeLedgerApplication.java

  transaction/
    Transaction.java
    TransactionRepository.java
    TransactionService.java
    TransactionController.java
    dto/

  category/
    Category.java
    CategoryRepository.java
    CategoryService.java
    CategoryController.java
    dto/

  summary/
    MonthlySummaryService.java
    SummaryController.java
    dto/

  common/
    error/
    validation/
```

Why:

- Related files stay close together.
- Domain concepts remain visible.
- The structure scales better than large generic `controller/`, `service/`, and `repository/` folders.

## Frontend Organization

Use feature-oriented folders.

Planned shape:

```text
frontend/src/
  api/
    httpClient.ts
    transactionApi.ts
    categoryApi.ts
    summaryApi.ts

  features/
    dashboard/
    transactions/
    categories/
    summary/

  components/
    layout/
    ui/

  lib/
    date.ts
    money.ts
```

Guidelines:

- `api/` contains HTTP calls.
- `features/` contains feature-specific UI, hooks, and types.
- `components/ui/` contains reusable low-level components.
- `lib/` contains small formatting/helpers.

## Deployment Flexibility

The monorepo does not force one production hosting model.

Possible future options:

- Host frontend and backend separately.
- Let Spring Boot serve the built frontend.
- Run everything on a VPS with Docker Compose.

For MVP, focus on local development only.
