# Domain Model

This document describes the main business concepts. It is not a database schema yet, but it should guide the backend model and migrations.

## Current MVP Concepts

### Transaction

A transaction represents money movement.

For MVP, only expense transactions are supported. The model should still be ready for income transactions later.

Draft fields:

```text
id
transactionType   EXPENSE for MVP, INCOME later
amount
date
description
category
createdAt
updatedAt
```

Rules:

- Use `BigDecimal` for money in the backend.
- Amount must be positive.
- Date is required.
- Expense transactions should have a category.
- MVP creates only `EXPENSE` transactions.

### Category

A category organizes transactions.

Categories support a parent/child hierarchy:

```text
Top-level category: parentCategory = null
Subcategory:        parentCategory = another category
```

Draft fields:

```text
id
name
parentCategory nullable
createdAt
updatedAt
```

Example:

```text
Transport
  - Taxi
  - Parking

Food
  - Groceries
  - Restaurants
```

Rules:

- Category names cannot be blank.
- Duplicate category behavior must be decided during implementation.
- Expenses should usually be assigned to the most specific useful category.
- Summaries should be able to group subcategory spending under parent categories.

## Future Concepts

### Budget Allocation

Represents planned money for a category/subcategory in a month.

Draft fields:

```text
id
month
year
category
allocatedAmount
createdAt
updatedAt
```

### Budget Adjustment

Represents a manual increase or reduction to available money for a category/month.

Possible uses:

- unexpected income
- gift money
- bonus money
- correction
- moving money between categories

Draft fields:

```text
id
month
year
category
amount
reason
createdAt
updatedAt
```

### Category Balance / Carryover

Represents accumulated available money for a category over time.

Example:

```text
previous balance + monthly allocation + adjustments - expenses = current balance
```

This is future scope because it introduces rollover rules.

### User Account

Represents a user who owns categories, budgets, transactions, and settings.

Draft fields:

```text
id
email
displayName
createdAt
updatedAt
```

Authentication and account management are future scope.

## Open Questions

- Should duplicate category names be allowed under different parent categories?
- Should expenses be allowed on top-level categories, or only subcategories?
- Should income use categories, separate income sources, or both?
- How should overspending affect carryover balances?
