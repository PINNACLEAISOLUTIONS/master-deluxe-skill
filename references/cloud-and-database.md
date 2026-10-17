# Cloud Infrastructure & Database Architecture Reference

## 1. Database Engineering (Supabase & Neon Postgres)

- **Schema Discipline**:
  - Always use explicit data types, foreign keys, and indexes on frequently filtered columns.
  - Prefix constraints clearly (`pk_`, `fk_`, `idx_`, `chk_`).
- **Row-Level Security (RLS)**:
  - Enable RLS on every public Supabase table.
  - Define separate, restrictive policies for `SELECT`, `INSERT`, `UPDATE`, and `DELETE`.
- **Zero-Downtime Migrations**:
  - Add nullable columns or columns with defaults before updating code.
  - Use Neon instant database branches to run and test migration scripts against live schema clones before production rollouts.

---

## 2. Cross-App Automations (Zapier)

- **Workflow Chaining**:
  - When scraping leads or generating data, chain Zapier actions to route data automatically:
    - `Lead Discovered` ➔ `Validate Email` ➔ `Append to Google Sheet` ➔ `Notify Slack Channel`.
- **Idempotency**:
  - Always ensure automated triggers include a unique deduplication key (e.g. `lead_email` or `transaction_id`) to prevent duplicate processing.

---

## 3. Edge Compute & Cloudflare

- **Edge Routing**:
  - Use Cloudflare Workers for sub-10ms response times on API proxies, webhook validation, and token verification.
  - Store frequently accessed static or session configuration in Cloudflare KV key-value stores.
