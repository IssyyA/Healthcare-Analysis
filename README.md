# Healthcare-Analysis
This project details the development and analysis of an interactive Power BI dashboard focusing on patient admission, billing, and demographics data from various hospitals and insurance providers across the United States. The dataset, covering January 2019 to December 2024, was cleaned, transformed, and aggregated to track key performance indicators such as total patient admissions, total billing amount, average length of stay, and the most common medical conditions. The dashboard aims to provide healthcare administrators, financial analysts, and operational managers with comprehensive insights to optimize resource allocation, identify financial trends, and improve patient care strategies.

Insights and recommendations are provided on the following key areas:

Category 1: Patient Volume & Demographics

Category 2: Billing & Financial Performance

Category 3: Treatment & Condition Insights

Category 4: Provider & Geographic Trends

The dataset was cleaned, aggregated, and analyzed using Power Query and DAX formulas before being visualized in Power BI, creating a clean, modern, and fully navigable user interface.

[📊 Power BI Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiNWNjNTZmN2EtYjJhMC00MjMzLTlmYWUtOGZlNGNkYjEzNmMwIiwidCI6IjM0YzAxYWRhLTc5MDItNGQ2My04MjgyLThkYzRiZjhmNTUxZCJ9) 

# Dataset Description
The data model comprises five tables capturing patient admissions, billing records, and demographic information from various hospitals and insurance providers, designed in a star schema. This structure efficiently supports the analysis of key performance indicators over the specified period.

## Tables
* Fact Hospital: The central fact table containing granular details of each patient admission, including Billing Amount, Date of Admission, Discharge Date, Doctor, Length of Stay, and linking keys to other dimensions. This table also includes Hospital Latitude and Hospital Longitude for geographic analysis, and Patient ID for unique patient tracking.
* Dim Patient: A dimension table providing detailed patient demographics and admission characteristics such as Admission Type, Age, Age Bands, Blood Type, Condition, Gender, and Insurance Provider.
* Dim Hospital: A dimension table containing unique Hospital names and additional hospital-specific attributes.
* Dim Medication: A dimension table listing distinct Medication types prescribed during admissions.
* DateTable: A standard date dimension table used for time-based filtering and analysis, including Date, Day, DayNumber, Month, and Month sh (shorthand month name).

## Calculated Measures
* Total Patients: Count of unique patient admissions (derived from Patient ID in Fact Hospital).
* Total Billing Amount: Sum of all Billing Amount from Fact Hospital.
* Avg Length of Stay: Average of Length of Stay from Fact Hospital.
* Most Common Condition: Dynamically identifies the most frequent Condition from Dim Patient.
* % YoY Growth: Year-over-Year percentage change for Total Patients and Total Billing.
* DAX Measures: Pre-calculated KPIs for breakdowns by gender, age, state, condition, and provider, utilizing fields from the various dimension tables linked to Fact Hospital.

