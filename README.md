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
