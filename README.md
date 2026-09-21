# 📊 E-Commerce Financial Ledger Audit & Revenue Protection

## 📌 Executive Summary
An exhaustive financial audit conducted on a transactional ledger of over **500,000 records** for an online retail business. The objective was to validate reporting integrity, remediate systemic logging failures, and derive true revenue metrics for executive decision-making. 

The audit successfully protected and accounted for **£1,754,901.91** in legitimate guest revenue that was at risk of accidental deletion, while establishing formal systemic remediation controls across IT and database engineering.

---

## 🖼️ Executive Financial Dashboard
![Executive Financial Dashboard](dashboard.png)

---

## 🔍 Audit Methodology & Root-Cause Matrix
The transactional ledger was categorized across 5 systematic failure points (`AUD-01` through `AUD-05`) documented in the audit log before staging to `Clean_Transactions`:

| Audit Ref | Issue / Anomaly | Root Cause | Business & Financial Impact | IT / Systemic Remediation | Owner |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`AUD-01`** | Missing `CustomerID` | Guest checkout flows bypassing user account creation | £1.75M unassigned revenue; distorted customer LTV modeling | Generate mandatory guest UUID tokens & incentivize signup | Web / Marketing |
| **`AUD-02`** | Duplicate Records | Payment gateway retry loops and sync latency | Artificial inflation of order volume, sales units, and Gross Sales | Enforce composite UNIQUE constraint on (InvoiceNo, StockCode, Date) | DBA / Backend |
| **`AUD-03`** | Negative Quantities | Return transactions embedded in sales ledger | Blurs gross sales figures and risks top-line distortion | Isolate cancellations into dedicated Refund schema linked to InvoiceNo | ERP / Finance IT |
| **`AUD-04`** | Zero-Price Items | Damaged warehouse stock entered via POS | Distorts revenue metrics with warehouse shrinkage | Block 0.00 UnitPrice at POS; route write-offs strictly through WMS | Supply Chain / IT |
| **`AUD-05`** | Dirty Strings | Leading/trailing whitespace and manual notes | Breaks downstream ETL pipelines and causes sync errors | Implement regex validation and strict dropdowns at input layer | Software Team |

---

## 📈 Verified Key Performance Indicators (KPIs)
* **Gross Sales:** `£10,642,095.80` *(Total confirmed positive order volume)*
* **Total Returns:** `-£893,979.73` *(Actual customer refunds processed)*
* **Net Revenue:** `£9,748,116.07` *(True cash-inflow verified against bank settlement)*
* **Rescued Guest Revenue:** `£1,754,901.91` *(16.5% of gross sales rescued via integrity validation)*
* **Return Rate:** `8.40%` *(Operational benchmark within healthy e-commerce thresholds)*

---

## 🛠️ Tools & Techniques
* **Microsoft Excel:** Data Auditing, Audit Logging, Text Transformation (`TRIM`, `PROPER`), Logic Gates (`IFS`, `AND`), Financial Aggregations (`SUBTOTAL`, `COUNTIF`).
* **Data Governance:** Audit Trail creation, Source-to-Target mapping, Downstream Remediation Design.
