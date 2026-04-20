## sql-support-queries

> Real-world SQL queries for FinTech technical support debugging:- written from the perspective of a Support Engineer investigating live issues.

These queries simulate the kinds of database investigations a Support Engineer at a FinTech or SaaS company runs daily: failed transactions, user account issues, API errors logged to a database, duplicate records, and more.

**Stack:** PostgreSQL · SQL

---

## 📂 File Structure

```
sql-support-queries/
├── schema/
│   └── setup.sql              # Creates all tables and seeds sample data
├── queries/
│   ├── 01_failed_transactions.sql
│   ├── 02_user_account_lookup.sql
│   ├── 03_api_error_log_analysis.sql
│   ├── 04_duplicate_records.sql
│   ├── 05_payment_reconciliation.sql
│   └── 06_support_ticket_trends.sql
└── README.md
```

## 🗄️ Schema Overview

```sql
-- Core tables used across all queries
users             -- customer accounts
transactions      -- payment records
api_error_logs    -- API failures logged to DB
support_tickets   -- customer-reported issues
payments          -- payment processing records
```

---

## 🔍 Query Summaries

| File | Scenario | Key Concepts |
|---|---|---|
| `01_failed_transactions.sql` | Investigate why payments are failing | WHERE, GROUP BY, COUNT, date filtering |
| `02_user_account_lookup.sql` | Look up a user's full account history | JOINs, subqueries, COALESCE |
| `03_api_error_log_analysis.sql` | Find patterns in API 4xx/5xx errors | GROUP BY, HAVING, window functions |
| `04_duplicate_records.sql` | Detect and flag duplicate entries | ROW_NUMBER(), CTE, PARTITION BY |
| `05_payment_reconciliation.sql` | Reconcile payments vs transactions | LEFT JOIN, NULL checks, SUM |
| `06_support_ticket_trends.sql` | Analyse ticket volume by category | DATE_TRUNC, aggregations, ORDER BY |

---

## 💡 How to Use

```bash
# 1. Start PostgreSQL
psql -U postgres

# 2. Create database
CREATE DATABASE support_db;
\c support_db

# 3. Run schema + seed data
\i schema/setup.sql

# 4. Run any query file
\i queries/01_failed_transactions.sql
```

---

## 🎯 Skills Demonstrated

- PostgreSQL querying and data investigation
- Debugging real-world FinTech scenarios with SQL
- Writing readable, well-commented support queries
- Using CTEs, window functions, and JOINs for complex lookups

