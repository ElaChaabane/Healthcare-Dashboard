# Power BI Healthcare Dashboard Project

## Overview
This project demonstrates a comprehensive Power BI solution tailored for various decision makers within a healthcare organization. Each dashboard is customized to display specific objectives, KPIs, and DAX formulas that support strategic decision-making across different departments.

## Project Structure
- **project.pbix**: The Power BI project file containing all dashboards.
- **README.md**: This file, providing detailed project information.

## Dashboards and Key Features

### 1. Hospital or Healthcare System Executives (CEO, COO, CFO)
**Objective:**  
Provide an overview of the financial health, resource allocation, and operational performance.

**KPIs:**
- **Total Revenue:** Revenue generated by all services.
- **Departmental Resource Allocation:** Resources allocated and used by each department.
- **Cost vs. Revenue Analysis:** Compare total costs to revenue.
- **Service Growth Trends:** Track service utilization trends over time.

**DAX Formulas:**
- **Total Revenue:**
  ```DAX
  TotalRevenue = SUM('visits'[Treatment_Cost])
- **Departmental Resource Allocation:**
  ResourceAllocation = CALCULATE(SUM('visits'[Resource_Allocated]), 'visits'[Department_ID])

- **Cost vs. Revenue:**
  RevenueToCost = DIVIDE(SUM('visits'[Treatment_Cost]), SUM('visits'[Total_Cost]))

- **Service Growth:**
  ServiceGrowth = CALCULATE(COUNT('visits'[Visit_ID]), DATESINPERIOD('visits'[Visit_Date], MAX('visits'[Visit_Date]), -12, MONTH))
### 2. Medical Directors and Department Heads
**Objective:** 
Monitor staff performance, equipment utilization, and diagnostic/treatment effectiveness.
**KPIs:**
Provider Performance
Procedure Frequency
Equipment Usage
Diagnosis Accuracy




# Power BI Healthcare Dashboard Project

## Overview
This project demonstrates a comprehensive Power BI solution tailored for various decision makers within a healthcare organization. Each dashboard is customized to display specific objectives, KPIs, and DAX formulas that support strategic decision-making across different departments.

## Project Structure
- **project.pbix**: The Power BI project file containing all dashboards.
- **README.md**: This file, providing detailed project information.

## Dashboards and Key Features

### 1. Hospital or Healthcare System Executives (CEO, COO, CFO)
**Objective:**  
Provide an overview of the financial health, resource allocation, and operational performance.

**KPIs:**
- **Total Revenue:** Revenue generated by all services.
- **Departmental Resource Allocation:** Resources allocated and used by each department.
- **Cost vs. Revenue Analysis:** Compare total costs to revenue.
- **Service Growth Trends:** Track service utilization trends over time.

**DAX Formulas:**
- **Total Revenue:**
  ```DAX
  TotalRevenue = SUM('visits'[Treatment_Cost])
  ```
- **Departmental Resource Allocation:**
  ```DAX
  ResourceAllocation = CALCULATE(SUM('visits'[Resource_Allocated]), 'visits'[Department_ID])
  ```
- **Cost vs. Revenue:**
  ```DAX
  RevenueToCost = DIVIDE(SUM('visits'[Treatment_Cost]), SUM('visits'[Total_Cost]))
  ```
- **Service Growth:**
  ```DAX
  ServiceGrowth = CALCULATE(COUNT('visits'[Visit_ID]), DATESINPERIOD('visits'[Visit_Date], MAX('visits'[Visit_Date]), -12, MONTH))
  ```

### 2. Medical Directors and Department Heads
**Objective:**  
Monitor staff performance, equipment utilization, and diagnostic/treatment effectiveness.

**KPIs:**
- Provider Performance
- Procedure Frequency
- Equipment Usage
- Diagnosis Accuracy

**DAX Formulas:**
- **Provider Performance:**
  ```DAX
  ProviderPerformance = CALCULATE(COUNT('visits'[Visit_ID]), 'visits'[Provider_ID])
  ```
- **Procedure Frequency:**
  ```DAX
  ProcedureFrequency = CALCULATE(COUNT('visits'[Procedure_ID]), 'visits'[Department_ID])
  ```
- **Equipment Usage:**
  ```DAX
  EquipmentUsage = CALCULATE(COUNT('visits'[Procedure_ID]), 'visits'[Equipment_ID])
  ```
- **Diagnosis Accuracy:**
  ```DAX
  DiagnosisSuccessRate = DIVIDE(COUNT('visits'[Diagnosis_Success]), COUNT('visits'[Diagnosis_ID]))
  ```

### 3. Financial Managers
**Objective:**  
Control costs, monitor budget allocations, and ensure profitability.

**KPIs:**
- Average Cost per Department
- Insurance Reimbursement Rates
- Profitability per Service
- Operational Cost Trends

**DAX Formulas:**
- **Average Cost per Department:**
  ```DAX
  AvgCostDepartment = AVERAGE('visits'[Total_Cost])
  ```
- **Insurance Reimbursement Rates:**
  ```DAX
  InsuranceReimbursement = DIVIDE(SUM('visits'[Covered_Amount]), SUM('visits'[Treatment_Cost]))
  ```
- **Profitability per Service:**
  ```DAX
  Profitability = DIVIDE(SUM('visits'[Treatment_Cost]), SUM('visits'[Total_Cost]))
  ```
- **Operational Cost Trends:**
  ```DAX
  CostTrends = CALCULATE(SUM('visits'[Total_Cost]), DATESINPERIOD('visits'[Visit_Date], MAX('visits'[Visit_Date]), -12, MONTH))
  ```

### 4. Clinical Operations Managers
**Objective:**  
Improve operational efficiency and patient satisfaction.

**KPIs:**
- Operational Efficiency
- Patient Satisfaction
- Resource Utilization
- Follow-Up Rate

**DAX Formulas:**
- **Operational Efficiency:**
  ```DAX
  VisitsPerStaff = DIVIDE(COUNT('visits'[Visit_ID]), SUM('staff'[Hours_Worked]))
  ```
- **Patient Satisfaction:**
  ```DAX
  AvgSatisfaction = AVERAGE('visits'[Patient_Satisfaction_Score])
  ```
- **Resource Utilization:**
  ```DAX
  ResourceUtilization = DIVIDE(SUM('visits'[Resource_Used]), SUM('visits'[Resource_Allocated]))
  ```
- **Follow-Up Rate:**
  ```DAX
  FollowUpRate = DIVIDE(COUNT('visits'[Follow_Up_Date]), COUNT('visits'[Visit_ID]))
  ```

### 5. Human Resources (HR)
**Objective:**  
Make informed staffing decisions and address training needs.

**KPIs:**
- Staffing Levels by Department
- Provider Performance
- Training Needs
- Staff Turnover Rate

**DAX Formulas:**
- **Staffing Levels:**
  ```DAX
  StaffLevels = COUNT('staff'[Staff_ID])
  ```
- **Provider Performance:**
  ```DAX
  StaffPerformance = CALCULATE(COUNT('visits'[Visit_ID]), 'visits'[Provider_ID])
  ```
- **Training Needs:**
  ```DAX
  Underperformance = CALCULATE(COUNT('visits'[Visit_ID]), FILTER('staff', 'staff'[Performance] < 70))
  ```
- **Staff Turnover Rate:**
  ```DAX
  TurnoverRate = DIVIDE(COUNT('staff'[Left_Date]), COUNT('staff'[Hire_Date]))
  ```

### 6. Insurance Liaison or Contract Managers
**Objective:**  
Optimize reimbursement and manage relationships with insurance providers.

**KPIs:**
- Insurance Reimbursement Rates
- Visits per Insurance Provider
- Coverage vs. Treatment Costs
- Contract Negotiation Insights

**DAX Formulas:**
- **Insurance Reimbursement Rates:**
  ```DAX
  ReimbursementRate = DIVIDE(SUM('visits'[Covered_Amount]), SUM('visits'[Treatment_Cost]))
  ```
- **Visits per Insurance Provider:**
  ```DAX
  VisitsInsurance = CALCULATE(COUNT('visits'[Visit_ID]), 'visits'[Insurance_ID])
  ```
- **Coverage vs Treatment Costs:**
  ```DAX
  CoverageVsCost = DIVIDE(SUM('visits'[Covered_Amount]), SUM('visits'[Total_Cost]))
  ```
- **Negotiation Insights:**
  ```DAX
  AvgReimbursementRate = AVERAGE('visits'[Covered_Amount])
  ```

Coverage vs Treatment Costs:
DAXCopierCoverageVsCost = DIVIDE(SUM('visits'[Covered_Amount]), SUM('visits'[Total_Cost]))

Negotiation Insights:
DAXCopierAvgReimbursementRate = AVERAGE('visits'[Covered_Amount])
