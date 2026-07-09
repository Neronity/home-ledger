# Roadmap

This roadmap separates the first useful MVP from later product features.

## MVP - Expense Tracking with Category Hierarchy

Goal: create the first working full-stack expense flow.

Scope:

- Project structure
- PostgreSQL via Docker Compose
- Spring Boot backend
- React/Vite frontend
- Transaction persistence, expense-only initially
- Category/subcategory hierarchy
- Monthly expense list
- Monthly expense total
- Category/subcategory spending summary

## v0.2 - Category Manager and Basic Budgets

Goal: let users manage spending organization and planned monthly amounts.

Scope:

- Category Manager tab
- Create/edit/delete categories
- Create/edit/delete subcategories
- Monthly budgets per category/subcategory
- Budget remaining view for the current month

## v0.3 - Income and Budget Adjustments

Goal: account for money coming in and manual changes to monthly available amounts.

Scope:

- Add income transactions
- Add budget adjustment entries
- Increase/reduce available monthly category budget
- Track inflow/outflow/net totals

## v0.4 - Carryover / Envelope Budgeting

Goal: support category balances that continue across months.

Scope:

- Carry unused category balance month to month
- Show accumulated category balances
- Handle overspending rules
- Support savings-style category tracking

## v0.5 - Accounts and User-Owned Data

Goal: make the app personal/account-based.

Scope:

- Authentication
- Account Management tab
- User-owned categories
- User-owned transactions and budgets
- Optional household/member support

## Later Ideas

- Charts and trends
- Month-over-month reports
- CSV import/export
- Deployment
- Backups
- Mobile-friendly improvements
