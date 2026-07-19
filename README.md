# Clinical Laboratory Data & Tracking System

A fully normalized relational database layout designed to simulate a modern hospital Laboratory Information System (LIS). The schema securely tracks patient records and diagnostics, conforming strictly to Third Normal Form (3NF) relational database standards.

---

## 📊 Database Schema

The system manages critical clinical metrics across **5 core tables**:

| Table | Description |
| :--- | :--- |
| `patients` | Unique identifiers, demographics, and medical record numbers. |
| `specimens` | Sample tracking (blood, swab, tissue) and timestamps. |
| `analyzers` | Automated laboratory machinery metadata. |
| `test_results` | Diagnostic values, reference ranges, and panic value flags. |
| `qc_logs` | Daily control run measurements used for calibration rules. |


---

## 🚀 How to Run

### Step 1 — Setup Database
```bash
mysql -u root -p < database_setup/schema_ddl.sql


---

## 💡 Analytical Query Highlights

| # | Operational Insight Required | Applied SQL Features |
| :--- | :--- | :--- |
| **1** | Identify tests exceeding standard Turnaround Time (TAT > 4 hours) | `COUNT`, `AVG`, `TIMESTAMPDIFF`, `GROUP BY` |
| **2** | Filter critical "Panic Values" for immediate physician notification | `WHERE`, `JOIN x3`, `CASE WHEN` |
| **3** | Detect instrument calibration drift based on daily standard deviations | `SUM`, `AVG`, `STDDEV`, `HAVING` |

---

## 🛠️ Full Architecture Notes

* **Referential Integrity Constraints:** Cascading deletions are blocked via Foreign Key constraints to protect historical patient diagnostic records from accidental deletion.
* **Zero-Downtime Safe Re-run:** The deployment script checks for preexisting database structures before rebuilding, simulating a secure live hospital server update environment.
