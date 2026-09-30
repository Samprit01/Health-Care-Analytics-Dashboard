# Health Care Analytics Dashboard

## Project Overview
This project is a Power BI-based data analysis and interactive dashboard designed to evaluate hospital operations, patient admissions, clinical outcomes, and treatment expenditures. The analysis covers 1,200 patient admission records spanning from 01 January 2024 to 31 August 2026 across 5 hospitals and 8 medical departments. By leveraging DAX measures, calculated columns, and interactive visualizations, the dashboard provides a centralized view of patient volume, hospitalization duration, treatment costs, and recovery patterns.

---

## Key Insights & Findings
- **Total Records Analyzed**: 1,200 patient admission records (displayed as 1K on the KPI card).
- **Total Treatment Cost**: ₹73,380,200.00 (~₹73.38M), with an average treatment cost of ₹61,150.17 per patient.
- **Average Length of Stay**: 4.53 days across all admissions, with the 3–5 Days group representing the largest patient cohort (474 patients / 39.50%).
- **Highest Volume & Cost Departments**: Dermatology recorded the highest patient volume at 180 admissions (15.00%), while Oncology incurred the highest total treatment expenditure at ₹15,147,000 (~₹15.15M, or 20.64% of total cost).
- **Leading Healthcare Facility**: Green Valley Hospital leads the dataset with 265 patient admissions (22.08%) and a total billing amount of ₹16,510,400.
- **Top Medical Diagnoses**: COVID-19 (101 cases), Heart Disease (99 cases), and Gastritis (95 cases) are the most frequent primary diagnoses.
- **Patient Demographics & Outcomes**: Male patients account for 53.58% of admissions (643) and Female patients represent 46.42% (557). Overall, 42.67% of patients (512) fully recovered and 28.58% (343) improved, alongside an average patient satisfaction score of 3.97 out of 5.0 (4,760.10 cumulative score).

---

## Dashboard Features
The interactive dashboard includes various components to facilitate deep-dive analysis:
- **KPI Cards**: Displays critical summary metrics including Total Patients (1K), Average Stay (4.53), Total Admissions (1K), Total Treatment Cost (73M), Recovery Rate (0.43), and Sum of Patient_Satisfaction (4.76K).
- **Departmental & Financial Analysis**: Visualizes patient headcount and total treatment cost breakdowns across all eight clinical departments.
- **Hospital & Diagnosis Insights**: Compares patient admission volumes across the five partner hospitals and ranks the 14 primary medical diagnoses.
- **Stay Duration Breakdown**: Maps out patient distribution across five length-of-stay bands using a stacked area chart.
- **Demographic & Outcome Monitoring**: Tracks gender ratios and clinical outcome distributions (Recovered, Improved, Stable, Complication, and Deceased) through donut charts.
- **Interactivity**: Includes top-level dropdown slicers for dynamic filtering by `Hospital`, `Admission_Year`, and `Department`, paired with a `Clear all slicers` action button.

---

## Data Structure & Key Calculations
The source data (`Healthcare_Data_Cleaned`) is maintained in a clean tabular structure at the record level using a unique `Patient_ID`. The primary DAX measures and calculated columns include:
- **Total Treatment Cost**: Calculated dynamically using the DAX formula: `SUM(Healthcare_Data_Cleaned[Treatment_Cost])`.
- **Recovery Rate**: Computes the proportion of recovered cases using: `DIVIDE(CALCULATE(COUNTROWS(Healthcare_Data_Cleaned), Healthcare_Data_Cleaned[Outcome]="Recovered"), COUNTROWS(Healthcare_Data_Cleaned))`.
- **Stay Group**: Automatically classifies `Length_of_Stay` into 1–2 Days, 3–5 Days, 6–10 Days, 11–15 Days, or 16–30 Days.

---

## Recommendations for Ongoing Use
- Refresh the Power BI data model whenever new patient admission or discharge records are added to the source Excel workbook so that all KPIs and visuals remain current.
- Use the Hospital, Admission_Year, and Department slicers to monitor complication cases (83 records) and readmissions (127 records) for targeted clinical quality improvement.
- Monitor high-expenditure departments, particularly Oncology, and review length-of-stay distributions to optimize bed allocation and hospital resource planning.


<img width="1328" height="747" alt="Dashboard preview" src="Health Care Analytics Dashboard Screenshot.jpg" />
