# hospital-patient-data-engineering
End-to-end hospital patient data processing using Databricks, PySpark, SQL, Delta Lake and Medallion Architecture.

# Hospital Patient Data Processing and Analytics

## Project Overview
This project demonstrates a batch ETL pipeline developed using Databricks, PySpark, SQL, and Delta Lake.

The pipeline processes synthetic hospital patient, appointment, and treatment data. It cleans and validates the records, stores them in Delta tables, and generates analytical datasets for hospital reporting.

## Technologies Used
- Databricks
- PySpark
- Spark SQL
- Delta Lake
- Unity Catalog
- Medallion Architecture
- Databricks AI/BI Dashboards

## Architecture
CSV Source Files → Bronze Layer → Silver Layer → Gold Layer → Databricks SQL Dashboard

## Bronze Layer
Ingested raw CSV files into three Delta tables:
- bronze_patients
- bronze_appointments
- bronze_treatments

## Silver Layer
Implemented transformations and validation rules including:
- Duplicate record removal
- Invalid and missing patient age detection
- Data type conversion
- Patient and appointment reference validation
- Negative treatment cost detection
- Rejected-record handling

Final cleaned datasets:
| Dataset | Records |
|---|---:|
| Patients | 50 |
| Appointments | 90 |
| Treatments | 43 |

## Gold Layer
Created three analytical Delta tables:

- gold_hospital_summary
- gold_department_analytics
- gold_daily_appointments

These provide hospital KPIs, department-wise appointment statistics, treatment cost totals, and daily appointment trends.

## Dashboard
Developed an interactive Databricks dashboard to display:

- Total registered patients: 50
- Total appointments: 90
- Total treatments: 43
- Total simulated treatment costs: ₹72,850
- Department-wise appointment distribution
- Daily appointment trends

## How to Run
1. Create a Databricks workspace.
2. Create a schema named `hospital_project`.
3. Create a Unity Catalog volume named `source_files`.
4. Upload the three synthetic CSV datasets.
5. Import the notebooks from the `notebooks` folder.
6. Update the catalog name if necessary.
7. Execute the Bronze, Silver, and Gold notebooks in sequence.
8. Use the Gold Delta tables to create the SQL dashboard.

## Execution Method
The pipeline is executed manually using Databricks notebooks. It uses full-table refreshes rather than scheduled or incremental processing.

## Data Privacy
All hospital patient data used in this project is synthetic and intended solely for educational purposes.

## Future Improvements
- Incremental data ingestion
- Automated pipeline orchestration
- Comprehensive duplicate and rejected-record auditing
- Expanded data-quality checks
- Automated testing

## Project Screenshots

See the `screenshots` folder for the completed Databricks dashboard.
