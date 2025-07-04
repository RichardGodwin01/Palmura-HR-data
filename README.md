# README

## Palmoria Group HR Analytics – Power BI Case Study

This project presents a comprehensive HR analytics solution for **Palmoria Group**, a Nigerian manufacturing company, using **Power BI**. The goal was to identify and address **gender-related disparities** and ensure compliance with labor regulations through data-driven insights.

---

## Project Objective

In response to public concerns about gender inequality, the CEO of Palmoria Group initiated this project to:

- Analyze gender distribution across regions and departments  
- Detect gender-based salary disparities  
- Evaluate compliance with minimum wage regulations  
- Automate bonus allocation based on performance ratings and department  

---

## Datasets

### 1. `Palmoria Group emp-data.csv`  
Employee-level data including:
- Gender  
- Department  
- Region  
- Performance Rating  
- Salary  

### 2. `Palmoria Group Bonus Rules.xlsx`  
Bonus rate matrix defined by:
- Department  
- Performance Rating  

---

## Project Workflow

### 1. Data Cleaning (Power Query)
- Removed ex-employees with null salaries  
- Dropped records with missing departments  
- Replaced missing gender values with `"Undisclosed"`  
- Cleaned and trimmed text fields (Department, Rating)  
- Created a `BonusKey` by merging Department and Rating  

### 2.Bonus Rules Transformation
- Unpivoted department columns into rows  
- Normalized data structure for lookup use  
- Created a matching `BonusKey` to align with employee data  

### 3. Data Modeling (Model View)
- Established a **one-to-many relationship** between:
  - `Employee[BonusKey]` and `Bonus Rules[BonusKey]`  

### 4. DAX Measures

DAX
Bonus Amount = RELATED('Bonus Rules'[Bonus Rate]) * 'Employee'[Salary]
Total Compensation = 'Employee'[Salary] + 'Employee'[Bonus Amount]
## Visuals & Insights

This section summarizes the key dashboards and insights generated from the HR analytics project.

### Gender Distribution
- Breakdown of employee gender across **regions** and **departments**
- Highlights departments or locations with gender imbalance

### Performance Rating Analysis
- Comparison of **performance ratings by gender**
- Identifies trends in employee evaluations across demographic lines

### Salary Analysis & Pay Gap
- Visual comparison of **average salary by gender**
- Detects any **gender-based pay disparities**
- Uses statistical visuals to reinforce equity findings

### Regulatory Compliance Check
- Identifies **employees earning below the $90,000 threshold**
- Flags regions or departments out of compliance with labor regulations

### Bonus Distribution
- Analyzes how **bonuses are allocated** by:
  - Department  
  - Performance rating  
  - Region  
  - Gender  
- Ensures fairness and consistency in the bonus calculation logic
