# 🏥 Healthcare Data Cleaning, Star Schema Modelling & Dashboard using Power BI

## 📌 Project Overview

This project focuses on cleaning healthcare data, building a **Star Schema Data Model**, and designing an interactive **Health Care Dashboard** using Microsoft Power BI. Power Query Editor is used to clean and transform healthcare records, dimension tables and a fact table are created for clinical data analysis, and the final model is visualized in a single-page report.

## 🎯 Objectives

- Clean and transform healthcare datasets using Power Query.
- Correct data types and standardize text values.
- Remove exact duplicate records.
- Categorize patients into age groups.
- Create dimension tables for patients, doctors, hospitals, and dates.
- Build a central FactAdmission table.
- Establish relationships using a Star Schema model.
- Design an interactive dashboard with KPI cards, slicers, and charts.

## 🛠️ Technologies Used

- **Microsoft Power BI Desktop**
- **Power Query Editor**
- **Power BI Model View**
- **Power BI Report View** (visuals, slicers, formatting)
- **CSV Dataset**

## 📂 Dataset Information

- **Dataset:** `healthcare_dataset(2).csv`
- **Original Records:** 55,500 rows
- **Columns:** 15

### Dataset Columns

- Name
- Age
- Gender
- Blood Type
- Medical Condition
- Date of Admission
- Doctor
- Hospital
- Insurance Provider
- Billing Amount
- Room Number
- Admission Type
- Discharge Date
- Medication
- Test Results

## 🧹 Data Cleaning and Transformation

The following operations were performed in Power Query:

1. Loaded the healthcare CSV dataset.
2. Renamed the base query to `Healthcare_Cleaned`.
3. Assigned appropriate data types to all columns.
4. Applied Trim and Clean operations to text columns.
5. Standardized patient names using Capitalize Each Word.
6. Removed 534 exact duplicate records.
7. Created an `AgeGroup` column.
8. Standardized admission types as Emergency, Elective, and Urgent.

### Age Group Categories

| Age Range | Category |
|---|---|
| 0–17 | Pediatric |
| 18–39 | Young Adult |
| 40–59 | Middle Adult |
| 60 and above | Senior |

## ⭐ Star Schema Data Model

The project contains six tables:

| Table Name | Purpose |
|---|---|
| `Healthcare_Cleaned` | Cleaned base dataset |
| `DimPatient` | Patient details and PatientID |
| `DimDoctor` | Doctor details and DoctorID |
| `DimHospital` | Hospital details and HospitalID |
| `DimDate` | Date, year, month, month number, and quarter |
| `FactAdmission` | Admission records and measurable details |

### Model Relationships

The `FactAdmission` table is connected to four dimension tables.

- `DimPatient[PatientID]` → `FactAdmission[PatientID]`
- `DimDoctor[DoctorID]` → `FactAdmission[DoctorID]`
- `DimHospital[HospitalID]` → `FactAdmission[HospitalID]`
- `DimDate[Date]` → `FactAdmission[Date of Admission]`

All four relationships use **one-to-many (1:*) cardinality** and single-direction cross-filtering.

## 📊 Dashboard

After building the star schema, an interactive **Health Care Dashboard** was created in Power BI Report View.

<img width="888" height="499" alt="Screenshot 2026-10-21 132834" src="https://github.com/user-attachments/assets/92f6a901-829d-4a1c-adb8-13b96e7654e1" />


### Dashboard Components

| Component | Visual Type | Description |
|---|---|---|
| Admission Type | Slicer (dropdown) | Filters the dashboard by Emergency, Elective, or Urgent admissions |
| Insurance Provider | Slicer (dropdown) | Filters the dashboard by insurance provider |
| Total Patients | KPI Card | Shows the total number of patients (~40K) |
| Average Age | KPI Card | Shows the average patient age (51.70) |
| Age Group vs Medical Condition | Matrix | Patient counts by age group (Pediatric, Young Adult, Middle Adult, Senior) across Arthritis, Asthma, Cancer, Diabetes, Hypertension, and Obesity |
| Total Admission by Hospital | Bar / Column Chart | Compares admission counts across hospitals |
| Total Admission by Year | Line (Area) Chart | Shows the admission trend from 2019 to 2024 |
| Total Admission by Admission Type | Pie Chart | Share of Emergency, Elective, and Urgent admissions |
| Total Admission by Age Group | Pie Chart | Share of admissions across the four age groups |
| Count of Gender by Year and Gender | Clustered Column Chart | Yearly patient count split by Female and Male |

### Design

- Dark navy theme with a yellow header banner for a clean healthcare look.
- Slicers placed at the top so every visual responds to the selected filters.
- KPI cards on the top-left for quick insights, followed by detailed charts.

### Dashboard Insights

- Admissions are almost evenly spread across Emergency, Elective, and Urgent types.
- The Senior age group has the highest patient counts across all medical conditions.
- Admission volume stays steady from 2020 to 2023; the drop in 2024 is likely due to partial-year data.

## 📈 Key Features

- Healthcare data cleaning and preprocessing
- Duplicate record removal
- Patient demographic categorization
- Standardized admission types
- Surrogate key generation
- Fact and dimension table creation
- Star Schema modelling
- Date dimension with year, month, and quarter
- Interactive dashboard with slicers, KPI cards, matrix, and charts
- Data model prepared for clinical analytics

## 🚀 How to Run the Project

1. Install and open Microsoft Power BI Desktop.
2. Download or obtain the healthcare CSV dataset.
3. Open Power BI Desktop.
4. Select **Home → Get Data → Text/CSV**.
5. Import `healthcare_dataset(2).csv`.
6. Select **Transform Data** to open Power Query Editor.
7. Follow the data cleaning and transformation steps.
8. Create the dimension tables and `FactAdmission`.
9. Create `DimDate` using Power Query Advanced Editor.
10. Select **Close & Apply**.
11. Open Model View and configure the four relationships.
12. Verify the final Star Schema.
13. Switch to Report View and build the dashboard: add the two slicers, KPI cards, the matrix, and the charts listed above.
14. Apply the navy and yellow formatting and save the `.pbix` file.

## 📈 Expected Outcome

A cleaned healthcare data model with patient, doctor, hospital, and date dimensions connected to a central admission fact table, along with an interactive dashboard that supports analysis by admission type, insurance provider, age group, medical condition, hospital, year, and gender.

## 🎓 Learning Outcomes

- Understanding data cleaning with Power Query
- Working with healthcare datasets
- Creating dimension and fact tables
- Generating surrogate keys
- Understanding Star Schema architecture
- Creating and managing Power BI relationships
- Designing interactive dashboards with slicers, KPI cards, and charts

## 📁 Repository Structure

```
├── healthcare_dataset(2).csv
├── Healthcare_Dashboard.pbix
├── PowerBI_Healthcare_Star_Schema_Guide.pdf
├── images/
│   └── dashboard.png
└── README.md
```

## 👨‍💻 Project Type

Academic / Data Analytics Project

## 📄 Documentation

Refer to `PowerBI_Healthcare_Star_Schema_Guide.pdf` for the detailed, step-by-step implementation guide.


