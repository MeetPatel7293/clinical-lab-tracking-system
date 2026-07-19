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
Run the schema DDL script in your MySQL terminal to initialize the database structures and mock tracking data.

### Step 2 — Run Queries
Execute the operational diagnostic metrics scripts to evaluate lab turnaround times.

---

## 💡 Analytical Query Highlights

* **Insight 1:** Identify tests exceeding standard Turnaround Time (TAT > 4 hours) using COUNT and AVG functions.
* **Insight 2:** Filter critical "Panic Values" for immediate physician notification using multi-table JOINs.
* **Insight 3:** Detect instrument calibration drift based on daily standard deviations using STDDEV and HAVING clauses.

---

## 🛠️ Full Architecture Notes

* **Referential Integrity Constraints:** Cascading deletions are blocked via Foreign Key constraints to protect historical patient diagnostic records from accidental deletion.
* **Zero-Downtime Safe Re-run:** The deployment script checks for preexisting database structures before rebuilding, simulating a secure live hospital server update environment.

---

## 🧠 Skills Demonstrated

`MySQL` `SQL DDL` `Relational Modeling` `3NF Normalization` `Clinical Analytics` `Database Architecture`
