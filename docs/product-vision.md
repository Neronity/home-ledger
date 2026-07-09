# Product Vision

Home Ledger should become a personal/household budgeting ledger for tracking day-to-day money movement, understanding spending patterns, and managing category-based budgets over time.

The MVP is intentionally smaller. This document describes the long-term direction.

## Main App Areas

The finished product should have three main tabs/views.

### 1. Dashboard

Main overview for the current month.

Expected capabilities:

- Monthly spending summary
- Category spending breakdown
- Subcategory spending breakdown
- Budget remaining by category/subcategory
- Carryover/savings visibility
- Later: charts and trends

### 2. Category Manager

Configuration area for organizing spending.

Expected capabilities:

- Create/edit/delete custom categories
- Create/edit/delete subcategories
- Set monthly budgets per category or subcategory
- View category budget configuration
- Later: archive categories without losing history

Example hierarchy:

```text
Miscellaneous
  - Taxi
  - Parking
  - Household items

Food
  - Groceries
  - Restaurants
  - Coffee
```

### 3. Account Management

User/account area for personal settings.

Expected capabilities:

- User profile/settings
- User-owned categories
- Future authentication
- Future household/member support if needed

## Long-Term Capabilities

### Category and Subcategory Tracking

Transactions should be assigned to the most specific useful category, usually a subcategory.

Dashboards should be able to show both:

```text
Miscellaneous: $120
  Taxi: $80
  Parking: $40
```

### Monthly Budgets

Users should be able to assign a budget to a category or subcategory for a month.

Example:

```text
Food budget for July: $500
```

### Budget Carryover

Unused money should be able to carry into later months instead of disappearing.

Example:

```text
June leftover Food balance: $80
July Food budget: $500
July available Food balance: $580
```

This makes the app closer to an envelope-budgeting system.

### Income and Adjustments

The app should eventually support money coming in, not only expenses.

Examples:

- Gifts
- Bonuses
- Selling old items
- Other unexpected income
- Manual budget increases/reductions

Income and adjustment support should help modify available money for the current month without breaking expense history.

### User-Owned Configuration

Custom categories, budgets, and account settings should eventually belong to a user account.

Authentication is not part of the MVP.

## Early Non-Goals

These are not early priorities:

- Bank integrations
- Receipt scanning
- Mobile app
- Complex analytics
- Multi-user household permissions
- Production deployment automation
