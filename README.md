#  HealthConnect Clinic — Patient No-Show Reduction Project

## Project Overview
HealthConnect Clinic is a fictional healthcare provider facing a significant patient appointment no-show problem. This is a multi-week shared project across AnalystLab Africa's internship tracks (Project Management, Data Analytics, Data Science, Machine Learning Engineering, and Generative AI), with each track contributing its own perspective toward a common goal: **reducing missed appointments and improving the patient support experience using data and AI.**

This repository documents the **Data Analytics track's** contribution, which will grow week by week as the project progresses through its stages: Problem Understanding → Analysis and Solution Design → Development → Testing and Refinement → Final Presentation.

**Track:** Data Analytics | AnalystLab Africa Experience Lab
**Prepared by:** Ndidiamaka Umahi
**Tools Used:** Power BI, Microsoft Word

## Files in This Repository
| File | Description |
|---|---|
| `HealthConnect_Appointment_Data.csv` | Original appointment dataset (5,000 records, 18 variables) — unmodified, as provided |
| `HealthConnect_Data_Dictionary.xlsx` | Variable definitions and structure reference — unmodified, as provided |
| `HealthConnect_Week4_DataAnalytics_InitialAnalysis.pdf` | Week 4 deliverable: dataset review, data quality assessment, business questions, proposed KPIs, initial analysis approach, and assumptions/limitations/risks |

## Dataset Description
| Column | Description |
|---|---|
| `appointment_id`, `patient_id` | Unique identifiers |
| `gender`, `age`, `age_group` | Patient demographics |
| `appointment_type` | Follow-up, Specialist Consultation, General Consultation, Diagnostic Test |
| `booking_date`, `appointment_date`, `appointment_day`, `appointment_time`, `booking_lead_days` | Scheduling details |
| `previous_appointments`, `previous_no_shows` | Patient attendance history |
| `reminder_sent`, `reminder_channel` | Reminder details (SMS, WhatsApp, Email) |
| `distance_to_clinic_km`, `waiting_time_minutes` | Access and wait-time factors |
| `appointment_outcome` | Attended, No-Show, or Cancelled — the target variable |

## Week 4 — Problem Understanding & Initial Analysis

### Data Quality Assessment
- **5,000 records, 18 columns** — no duplicate rows, no duplicate appointment IDs
- **Missing values**: `reminder_channel` (27.3% missing, fully explained by `reminder_sent = "No"`), `distance_to_clinic_km` (1.8% missing), `waiting_time_minutes` (1.2% missing)
- **Logic checks passed**: no patient has more previous no-shows than previous appointments; no booking date occurs after its appointment date
- **Outcome distribution**: No-Show 48.5% · Attended 46.3% · Cancelled 5.3% — an unusually high no-show rate confirming the severity of the business problem

### Business Questions
1. What is the overall no-show rate, and how does it compare across outcomes?
2. Does distance to the clinic affect no-show likelihood?
3. Does sending a reminder — and which channel — reduce no-shows?
4. Does a patient's previous no-show history predict future no-shows?
5. Does booking lead time affect attendance?
6. Do appointment type, day, or time relate to no-show rate?
7. Does age or age group relate to no-show likelihood?

### Proposed KPIs
| KPI | Business Question |
|---|---|
| Overall No-Show Rate | Q1 |
| No-Show Rate by Reminder Status/Channel | Q3 |
| No-Show Rate by Previous No-Show History | Q4 |
| Average Distance to Clinic (No-Show vs Attended) | Q2 |
| No-Show Rate by Booking Lead Time | Q5 |

### My Role in the Broader Project
As the Data Analytics track, my work provides the analytical foundation for the wider HealthConnect project — patterns identified here (particularly reminder effectiveness and previous no-show history) are expected to directly inform the Data Science track's predictive modeling, while insights into patient behavior may inform the Generative AI track's assistant design.

##  Assumptions & Limitations
- Dataset is fictional/synthetic; findings are illustrative, not directly actionable for a real clinic
- No "reason for no-show" field exists, limiting root-cause depth
- `distance_to_clinic_km` and `waiting_time_minutes` have a small number of missing values with no identified explanatory pattern

## Proposed Focus for Week 5
Execute data preparation (handling the two fields with missing values) and begin exploratory analysis, starting with no-show rate broken down by previous no-show history and reminder channel.

---
*This README will be updated each week as the HealthConnect project progresses.*
