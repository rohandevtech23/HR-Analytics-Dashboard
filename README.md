# HR Attrition & Workforce Intelligence Dashboard

## Project Overview

This project analyzes employee attrition using Excel, PostgreSQL, SQL, Power BI, and DAX. The goal is to identify why employees leave the company, which departments and job roles have higher attrition, and which employee groups are at higher risk of leaving.

Attrition means employees leaving the company. In this project, `Attrition = Yes` means the employee left, and `Attrition = No` means the employee is still active.

## Business Objective

The main objective of this project is to help HR teams answer:

- What is the overall attrition rate?
- Which departments have the highest attrition?
- Which job roles are most affected?
- Does overtime impact attrition?
- Does salary band influence attrition?
- Are newer employees leaving more?
- Does job satisfaction affect attrition?
- Which employees are at high risk of leaving?

## Tools Used

- Excel
- PostgreSQL
- SQL
- Power BI
- DAX

## Dataset

The project uses the IBM HR Analytics Employee Attrition dataset.

Dataset size:

- 1470 rows
- 35 original columns

Important columns:

- Age
- Attrition
- Department
- Gender
- JobRole
- MonthlyIncome
- OverTime
- JobSatisfaction
- WorkLifeBalance
- YearsAtCompany
- YearsSinceLastPromotion
- TrainingTimesLastYear

## Data Cleaning

Data cleaning was done in Excel.

Steps performed:

- Checked missing values
- Checked duplicate records
- Removed constant-value columns
- Created new calculated columns
- Saved cleaned data as CSV for PostgreSQL import

Removed columns:

- EmployeeCount
- Over18
- StandardHours

These columns were removed because they had constant values and did not add analytical value.

## Feature Engineering

New columns created:

- Age Group
- Salary Band
- Tenure Group
- Promotion Status
- Overtime Flag
- Attrition Flag

## SQL Analysis

The cleaned dataset was imported into PostgreSQL. SQL was used to analyze:

- Total employees
- Attrition count
- Attrition rate
- Department-wise attrition
- Job role-wise attrition
- Overtime impact
- Salary band attrition
- Tenure group attrition
- Promotion impact

## Employee Risk Model

A SQL view was created to classify employees into risk categories.

Risk factors used:

- Overtime = Yes
- Job Satisfaction <= 2
- Work Life Balance <= 2
- Years At Company <= 2
- Years Since Last Promotion >= 3
- Monthly Income < 5000

Risk categories:

- Critical Risk
- High Risk
- Medium Risk
- Low Risk

Risk model result:

| Risk Category | Total Employees | Attrition Count | Attrition Rate |
|---|---:|---:|---:|
| High Risk | 106 | 54 | 50.94% |
| Critical Risk | 9 | 3 | 33.33% |
| Medium Risk | 841 | 152 | 18.07% |
| Low Risk | 514 | 28 | 5.45% |

## Power BI Dashboard Pages

### 1. Executive Overview

Shows high-level HR KPIs:

- Total Employees
- Active Employees
- Attrition Count
- Attrition Rate
- Average Salary
- Average Job Satisfaction
- High Risk Employees
- Average Risk Score

### 2. Attrition Driver Analysis

Analyzes attrition by:

- Overtime
- Salary Band
- Tenure Group
- Job Satisfaction
- Work Life Balance
- Promotion Status

### 3. Compensation & Salary Analysis

Analyzes salary patterns by:

- Salary Band
- Job Role
- Department
- Gender
- Job Level
- Total Working Years

### 4. Career Growth Analysis

Analyzes career-related factors:

- Promotion Status
- Years Since Last Promotion
- Years in Current Role
- Training Times
- Career stagnation by department

### 5. Employee Risk Model

Shows employee risk segmentation using the SQL risk model.

Visuals include:

- Attrition Rate by Risk Category
- Employee Count by Risk Category
- High and Critical Risk Employees by Department
- Risk Category by Job Role
- Risk Score vs Monthly Income

## Key Insights

- Overall attrition rate is 16.12%.
- Sales and Human Resources show higher attrition rates.
- Sales Representative has one of the highest job-role attrition rates.
- Employees with 0-2 years tenure have the highest attrition among tenure groups.
- Overtime, low satisfaction, low salary, and short tenure are strong attrition indicators.
- High Risk employees show 50.94% attrition, compared to only 5.45% among Low Risk employees.

## Business Recommendations

- Focus retention strategies on High Risk and Critical Risk employees.
- Investigate overtime workload in high-attrition departments.
- Review compensation for low-salary employees in high-risk roles.
- Improve onboarding and engagement for employees in the 0-2 years tenure group.
- Track job satisfaction and work-life balance regularly.
- Use the risk model as an early warning system for HR intervention.

