# Healthcare-Analysis
This project details the development and analysis of an interactive Power BI dashboard focusing on patient admission, billing, and demographics data from various hospitals and insurance providers across the United States. The dataset, covering January 2019 to December 2024, was cleaned, transformed, and aggregated to track key performance indicators such as total patient admissions, total billing amount, average length of stay, and the most common medical conditions. The dashboard aims to provide healthcare administrators, financial analysts, and operational managers with comprehensive insights to optimize resource allocation, identify financial trends, and improve patient care strategies.

Insights and recommendations are provided on the following key areas:

Category 1: Patient Volume & Demographics

Category 2: Billing & Financial Performance

Category 3: Treatment & Condition Insights

Category 4: Provider & Geographic Trends

The dataset was cleaned, aggregated, and analyzed using Power Query and DAX formulas before being visualized in Power BI, creating a clean, modern, and fully navigable user interface.

[📊 Power BI Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiNWNjNTZmN2EtYjJhMC00MjMzLTlmYWUtOGZlNGNkYjEzNmMwIiwidCI6IjM0YzAxYWRhLTc5MDItNGQ2My04MjgyLThkYzRiZjhmNTUxZCJ9) 

## Dataset Description
The data model comprises five tables capturing patient admissions, billing records, and demographic information from various hospitals and insurance providers, designed in a star schema. This structure efficiently supports the analysis of key performance indicators over the specified period.

### Tables
* Fact Hospital: The central fact table containing granular details of each patient admission, including Billing Amount, Date of Admission, Discharge Date, Doctor, Length of Stay, and linking keys to other dimensions. This table also includes Hospital Latitude and Hospital Longitude for geographic analysis, and Patient ID for unique patient tracking.
* Dim Patient: A dimension table providing detailed patient demographics and admission characteristics such as Admission Type, Age, Age Bands, Blood Type, Condition, Gender, and Insurance Provider.
* Dim Hospital: A dimension table containing unique Hospital names and additional hospital-specific attributes.
* Dim Medication: A dimension table listing distinct Medication types prescribed during admissions.
* DateTable: A standard date dimension table used for time-based filtering and analysis, including Date, Day, DayNumber, Month, and Month sh (shorthand month name).

### Calculated Measures
* Total Patients: Count of unique patient admissions (derived from Patient ID in Fact Hospital).
* Total Billing Amount: Sum of all Billing amount from Fact Hospital.
* Avg Length of Stay: Average of Length of Stay from Fact Hospital.
* Most Common Condition: Dynamically identifies the most frequent Condition from Dim Patient.
* % YoY Growth: Year-over-Year percentage change for Total Patients and Total Billing.
* DAX Measures: Pre-calculated KPIs for breakdowns by gender, age, state, condition, and provider, utilizing fields from the various dimension tables linked to Fact Hospital.
![image](https://github.com/IssyyA/Healthcare-Analysis/blob/main/Screenshot%202025-08-25%20155919.png)

## Executive Summary

### Overview of Findings
Between 2019 and 2024, the analyzed healthcare system experienced consistent growth in patient volume and billing revenue. While the average length of stay remained stable, key insights emerged regarding the prevalence of chronic conditions, financial contributions of major providers and insurers, and demographic patterns.

*   A total of **55,500 patients** were served, generating **$1.42 billion** in total billing, both showing a healthy **7% Year-over-Year (YoY)** increase.
*   The **average length of stay** remained consistent at **15.51 days**.
*   **Hypertension** was identified as the **most common medical condition**.
*   Patient admissions showed a clear **quarterly trend**, typically peaking in **Q3**.
*   **Houston Hospital** and **Johns Hopkins** consistently managed the highest patient volumes and billing amounts.

### Insights Deep Dive

**Category 1: Patient Volume & Demographics**
*   **Total Patient Volume:** The dashboard tracked 55,500 patient admissions over the period, demonstrating a 7% YoY increase, indicating expanding service reach or rising healthcare demand.
*   **Gender Distribution:** Admissions were largely balanced, with Males accounting for 50%, Females 40%, and a notable 10% identifying as Non-binary, highlighting the importance of inclusive data capture.
*   **Age Groups:** The 20-29 age bracket consistently showed the highest patient volume (e.g., 1,545 patients in 2021 as seen in the Demographics tab), suggesting a high engagement of young adults with the healthcare system, potentially for acute conditions or initial diagnoses.
*   **Geographic Reach:** Analysis by state reveals higher patient densities in states like California, Texas, and Florida (indicated by darker shading on the map), suggesting a concentration of services or higher population healthcare needs in these regions.
*   **Quarterly Trends:** Admitted patients showed a clear seasonal trend, with volumes typically increasing from Q1 to a peak in Q3 (e.g., 14.19K in Q3) before a slight decline in Q4. This pattern could inform staffing and resource planning.

![image](https://github.com/IssyyA/Healthcare-Analysis/blob/main/Screenshot%202025-08-25%20153001.png)

**Category 2: Billing & Financial Performance**
*   **Total Billing:** A substantial $1.42 billion was billed across all services, reflecting a robust 7% YoY increase, aligning with the rise in patient volume.
*   **Billing by Condition:** Diabetes and Hypertension consistently generated the highest billing amounts, indicating the significant cost burden associated with managing these chronic conditions. Obesity also contributed substantially.
*   **Insurance Providers:** Medicare and Aetna were the dominant insurance providers by total billing amount, accounting for the largest share of revenue, highlighting their critical role in the financial ecosystem.
*   **Hospital Billing Contribution:** Houston Hospital recorded the highest total billing amount, followed by Johns Hopkins and UCLA, mirroring their high patient volumes and comprehensive service offerings.
*   **Monthly Billing Trends:** The "Billing Amount by Month" visual further illustrates the financial contribution of top hospitals, with Houston leading significantly, followed by Johns and UCLA.

![image](https://github.com/IssyyA/Healthcare-Analysis/blob/main/Screenshot%202025-08-25%20153013.png)

**Category 3: Treatment & Condition Insights**
*   **Most Common Condition:** Hypertension was identified as the most prevalent condition across all patient admissions, underscoring its widespread impact on public health.
*   **Condition-Specific Hospital Loads:** Hospitals like Houston showed significant patient numbers across multiple prevalent conditions such as Hypertension, Diabetes, and Obesity, positioning them as major treatment centers for these chronic diseases. Johns Hopkins demonstrated high patient counts for Arthritis and Hypertension.
*   **Medication Insights:** The dashboard provides a valuable breakdown of medication usage per condition (e.g., Aspirin, Ibuprofen, Paracetamol for Hypertension), offering insights into common treatment protocols and potential areas for cost-effectiveness analysis for specific drugs.

**Category 4: Provider & Geographic Trends**
*   **Top Performing Hospitals:** Houston Hospital consistently leads in both patient volume (e.g., 20.40K patients) and total billing, followed by Johns Hopkins (11.27K patients). This indicates these institutions are major hubs for patient care and likely operate under significant operational pressure.
*   **Hospital Specialization/Focus:** The matrix comparing hospitals against conditions (e.g., Arthritis, Asthma, Cancer, Diabetes, Hypertension, Obesity) allows for quick identification of hospitals that handle a disproportionate share of specific conditions, suggesting areas of specialization or regional demand.
*   **Geographic Hotspots:** The map visual on the Demographics page quickly identifies states with the highest patient admissions, guiding strategic planning for service expansion or targeted public health campaigns.

### Recommendations

Based on these insights, the following recommendations are put forth:

*   **Targeted Outreach for High-Volume Conditions:** Develop specific public health programs, preventative care initiatives, and resource allocation strategies for conditions like Hypertension and Diabetes, given their high prevalence and significant billing impact.
*   **Resource Optimization for Key Providers:** Prioritize staffing, funding, and infrastructure investments for high-volume hospitals (e.g., Houston, Johns Hopkins) to ensure sustained quality of care and prevent burnout.
*   **Seasonal Staffing Adjustments:** Implement flexible staffing models and resource planning to accommodate the observed quarterly surges in patient admissions, particularly peaking in Q3.
*   **Insurance Negotiation & Partnership Strategy:** Leverage insights into dominant insurance providers (Medicare, Aetna) to optimize billing cycles, negotiation strategies, and potential partnership opportunities.
*   **Demographic-Specific Care Pathways:** Design and promote age-group and state-specific healthcare programs, especially for the high-volume 20-29 age bracket and states with high patient density, to address their unique healthcare needs effectively.
*   **Medication Formulary Review:** Utilize medication usage data to review formulary effectiveness, cost-efficiency, and adherence rates for common conditions, potentially identifying areas for improvement in patient outcomes and cost savings.

### Assumptions

*   Data completeness and accuracy from the source hospital and insurance provider systems are assumed post-cleaning.
*   All Key Performance Indicators (KPIs) and measures are calculated based solely on the provided dataset without external imputation.
*   The analysis reflects performance and trends specifically within the January 2019 – December 2024 timeframe, and extrapolation beyond this period should be done with caution.
*   The classification of patient conditions and demographic data is consistent across all data sources.


