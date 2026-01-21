# 🏥 Hospital Early Warning System – Microsoft Fabric

## Overview
End-to-end data engineering project built on Microsoft Fabric using Medallion Architecture to support clinical early-warning analytics.
---

## 🏗️ Medallion Architecture

| Layer   | Description |
|---------|-------------|
| **Bronze** | Raw ingestion from CSV files on GitHub into Lakehouse tables. |
| **Silver** | Cleansed and enriched tables (patients, labs, vitals) with validations and transformations. |
| **Gold**   | Domain-specific tables for Doctors and Nursing teams: <br>• `gold_doctors_data` <br>• `gold_doctors_data` |

---

## 👩‍⚕️ Domains

### 1️⃣ Doctors Workspace (Hospital-Clinical)
- Audience: Doctors
- Exposed tables: `gold_doctors_data`
- Reporting: Power BI report showing abnormal labs and patient status.

### 2️⃣ Nursing Workspace (Hospital-Nursing)
- Audience: Nursing staff
- Exposed tables: `gold_nursing_data`
- Reporting: Power BI report showing vital signs alerts and nurse interventions.

> Workspaces reference the **same central Lakehouse** to avoid duplication, ensuring data consistency and governance.

---

## 📊 Reporting Layer (Proof of Consumption)

**Doctors Report:**
- Table: patient_id, wbc_status
- Bar Chart: Distribution of WBC status

 📌 Screenshots stored in `docs/screenshots/`

**Nursing Report:**
- Table: patient_id, hour_from_admission, vitals_instability_flag, nurse_alert
- Line Chart: Hourly alerts

📌 Screenshots stored in `docs/screenshots/`

---

## ✅ Data Quality & Observability
- Validations on vitals and lab ranges
- Incremental ingestion checks
- Pipeline logs capturing:
  - run time
  - status
  - rows processed

---

## ⚡ How to Run
1. Clone the repo:
```bash
git clone https://github.com/YOUR_USERNAME/hospital-fabric-project.git
