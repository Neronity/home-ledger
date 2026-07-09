# Development Workflow

Use GitHub Issues and a simple project board to guide work.

## Board Columns

```text
Backlog -> Ready -> In Progress -> Done
```

## Labels

Recommended labels:

```text
setup
backend
frontend
database
docs
feature
bug
refactor
testing
learning
priority: high
priority: medium
priority: low
```

## Milestones

```text
MVP Foundation + Expense Vertical Slice
v0.2 Category Manager and Basic Budgets
v0.3 Income and Budget Adjustments
v0.4 Carryover / Envelope Budgeting
v0.5 Accounts and User-Owned Data
```

## Feature Workflow

For each feature:

1. Create or choose a GitHub issue.
2. Create a feature branch.
3. Implement backend/domain logic first when relevant.
4. Add basic tests for business logic.
5. Add frontend UI.
6. Update docs if a decision changed.
7. Merge to `main`.

## Branch Examples

```text
feature/project-skeleton
feature/category-hierarchy
feature/transaction-api
feature/monthly-summary
docs/update-product-plan
```

## Commit Examples

```text
feat: add category hierarchy entity
feat: add expense transaction endpoint
feat: add monthly spending summary
fix: correct category summary grouping
docs: update MVP scope
```

## Working Agreement

- Keep MVP issues focused.
- Prefer small vertical slices over large rewrites.
- Keep business logic in backend services, not controllers or frontend components.
- Use docs to record decisions, not every implementation detail.
- Update planning docs when product scope changes.
