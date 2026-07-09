# MVP Scope

The MVP should prove the first useful full-stack flow:

```text
Create expense transaction -> save to database -> display monthly expense list and summary
```

## Goal

Build a small working expense tracker using the long-term transaction/category model without implementing every future budgeting feature.

## Included in MVP

- Project structure with separate `backend/` and `frontend/` apps
- PostgreSQL running locally with Docker Compose
- Spring Boot backend
- React/Vite frontend
- Transaction-based backend model
- Expense transactions only at first
- Category/subcategory hierarchy
- Add expense transactions manually
- Store amount, date, description, and category/subcategory
- View expense transactions for a selected month
- Show monthly expense total
- Show spending grouped by top-level category
- Show or prepare for subcategory breakdown

## Excluded from MVP

- Authentication
- Account management tab
- User-owned data
- Income entry
- Budget creation/editing
- Budget carryover
- Budget adjustments
- Charts
- Bank integrations
- Receipt scanning
- Deployment

## First Vertical Slice

```text
Add expense transaction
  -> persist transaction in PostgreSQL
  -> list transactions for selected month in UI
```

## MVP Success Criteria

- PostgreSQL starts locally.
- Backend starts and connects to PostgreSQL.
- Frontend starts locally.
- User can create an expense transaction from the UI.
- Expense transaction is persisted in the database.
- User can view expense transactions for a selected month.
- User can see the monthly total.
- User can see spending grouped by category/subcategory.

## MVP Issue Adjustments

Existing expense/category issues should be adjusted to support the updated model:

- Category persistence should support parent/child hierarchy.
- Expense persistence should use or prepare for a transaction-based model.
- Monthly summary should group by top-level category and optionally subcategory.
- Expense form should allow selecting a category/subcategory.
