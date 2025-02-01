# Delayed-Oil-Project

## Project Overview
---

**Objectives**

This project investigates the root causes of delays in the oil transfer process and proposes a strategic solution plan, analyzing operational workflow, resource Allocation, and efficiency, it seeks to identify trends and key areas for improvement 

**Scope**

**The Analysis Cover:**
  * Current transfer and handling protocols
  * Staffing and equipment utilization patterns
  * Services delay patterns and external influencing factors
  * Operational bottlenecks and improvement opportunities
  
**Methodology**
 - Data Collection: Gathering logs, staffing data, equipment status, and services records
 - Analysis: Identifying delay trends and correlating them with operation factors
 - Root Cause Analysis: Diagnosing main delay contributors
 - Solution Proposal: Recommending solutions, such as process optimization and resource allocation

---

### DATA SOURCE
The data set was provided by the client as a csv file, which was downloaded and processed for analysis.

**Tools**

- Microsoft Excel Utilized for preliminary data correction and initial review of the dataset.
- SQL Server: Employed for data cleaning in-depth analysis to extract meaningful insights.
- Power BI: Used to visualize insights and provide detailed, interactive reports

### EXPLORATORY DATA ANALYSIS (EDA)

---

**Key Question to Address:**
1. Total Number of Truck Drivers
   - Determine the number of truck drivers to assess if current staffing meets operational demands
2. Number of Efficient Trucks
   - Identify the count of trucks classified as efficient to understand fleet reliability and potential operational constraints
3. Coverage Areas (Distances in Kilometers)
   - Analyze distances covered to evaluate the geographic reach and the adequacy of logistical support across areas served
4. Truck Breakdown and Maintenance Frequency
   - Assess the frequency of truck breakdowns and scheduled maintenance to pinpoint areas needing additional support or preventive measures.

These insights from EDA will contribute to optimizing workforce planning, improving fleet management, and enhancing the overall efficiency of oil transfer services.

---

### USED SQL CODES

SQL
```SELECT COUNT(*) AS TotalTruckDrivers
FROM employees
WHERE job_title = 'Truck Driver';
SELECT COUNT(*) AS EfficientTrucks FROM trucks WHERE efficiency_status ='Efficient';
SELECT truck_id, SUM(distance_in_km) AS TotalDistanceCovered FROM deliveries GROUP By truck_id;
SELECT truck_id, COUNT(*) AS BreakdownCount FROM maintenance_log GROUP By truck_id;
SELECT truck_id, COUNT(*) AS Maintenance FROM maintenance_log GROUP By truck_id;
SELECT COUNT(*) AS EmployeesHiredInLastYear FROM employees WHERE hire_date >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR);
SELECT YEAR(hire_date) AS Year, MONTH(hire_date) AS Month, COUNT(*) AS EmployeesHired FROM employees GROUP BY YEAR(hired_date), MONTH(hire_date) ORDER BY YEAR(hired_date) DESC, MONTH(hired_date) DESC;

---

RECOMMENDATIONS
Based on the Exploratory Data Analysis (EDA) and insights derived from SQL queries, here are some recommendations to improve the efficiency and reliability of the oil transfer services:
1. Optimize Workforce Allocation:
    - Recommendation:
   o Based on the total number of truck drivers, assess if the current workforce is sufficient to meet demands, 
     especially during peak periods. if there are shortages, consider hiring additional drivers or redistributing work hours to avoid 
     delays.
   - Actionable Steps:
   o Evaluate whether the number of drivers matches the number of trucks and expected delivery volumes.
   o Consider flexible staffing models, such as on-demand or seasonal hires, to meet peak services to meet peak service needs.
