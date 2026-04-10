# Student Performance & Retention Analytics

## Problem Statement

Many students in online learning environments fail or withdraw from courses, leading to reduced institutional performance, inefficient resource usage, and poor academic outcomes. Institutions often lack real-time analytical tools to identify at-risk students and understand the factors influencing performance.

Manual analysis methods are insufficient when dealing with large-scale datasets containing millions of interaction records. This makes it difficult to detect meaningful patterns and intervene early.

This project addresses this gap by developing an interactive Power BI dashboard that enables stakeholders to monitor student engagement, identify risk patterns, and support data-driven decision-making to improve student retention and success rates.

---

# Business Questions

This project was designed to answer the following key questions:

1. What demographic factors influence student performance and retention?
2. How does academic workload affect student outcomes?
3. What role does Virtual Learning Environment (VLE) engagement play in student success?
4. Which students are at risk of failing or withdrawing?
5. How can institutions use predictive insights to improve student completion rates?
6. What interventions can be implemented to reduce dropout rates?

---

# Data Sources (with Links)

This project uses the **Open University Learning Analytics Dataset (OULAD)**, a publicly available dataset containing student demographics, engagement data, and assessment performance.

### Primary Dataset

Open University Learning Analytics Dataset (OULAD)  
Kaggle Source:  
https://www.kaggle.com/datasets/anlgrbz/student-demographics-online-education-dataoulad

### Key Tables Used

- **studentInfo**
  - Demographic details such as age, gender, region, disability status, and education level.

- **studentVle**
  - Records daily student interactions with online learning resources.

- **studentAssessment**
  - Stores assessment scores, submission timing, and academic performance.

- **vle**
  - Contains metadata about digital learning resources.

- **assessments**
  - Provides information about assessment weights and types.

- **courses**
  - Stores module and presentation details.

These datasets collectively contain:

- ~29,000 students (filtered cohort)
- Over 10.6 million VLE interaction records
- Multiple academic assessment records

This dataset structure supports detailed analysis of learning behavior and performance patterns. :contentReference[oaicite:0]{index=0}  

---

# Data Model Description

A **Star Schema data model** was implemented to optimize performance and improve analytical efficiency.

## Dimension Tables

- studentInfo  
  Contains student demographic attributes.

- vle  
  Stores information about digital learning resources.

- Dim_Date (Created using DAX)  
  Enables time-based analysis and trend visualization.

## Fact Tables

- studentVle  
  Stores daily interaction activity for students.

- studentAssessment  
  Contains student assessment submission and score data.

## Key Transformations

The data preparation process included:

- Replacing null values in assessment weights and scores.
- Converting age bands into numeric ranges.
- Splitting IMD deprivation bands into numeric values.
- Creating categorical variables such as:
  - performance_category
  - age_category
  - submission_period
- Creating standardized date structures using DAX.
- Establishing one-to-many relationships between dimension and fact tables.

These steps ensured a clean, structured model suitable for large-scale reporting and analysis. :contentReference[oaicite:1]{index=1}  

---

# DAX Highlights (3 Complex Measures)

## 1. At-Risk Students Measure

This measure identifies students who are likely to fail or withdraw based on engagement and performance thresholds.

Logic:

Students are flagged as **At-Risk** when:

- Average Score < 40  
AND  
- VLE Clicks < 100  

Purpose:

- Enables early intervention
- Identifies students needing academic support
- Supports retention planning

---

## 2. Completion Rate Measure

This measure calculates the percentage of students who successfully completed their course.

Logic:

Completion Rate =  
(Number of students with Pass or Distinction) ÷ (Total Students)

Purpose:

- Tracks institutional performance
- Supports monitoring of retention targets
- Provides KPI visualization in dashboards

---

## 3. What-If Retention Scenario

A dynamic parameter allowing simulation of retention improvement scenarios.

Range:

5% to 15% improvement

Purpose:

- Supports strategic planning
- Allows institutions to evaluate potential outcomes
- Enables data-driven policy testing

These advanced DAX calculations enhance the analytical capabilities of the dashboard and support predictive insights. :contentReference[oaicite:2]{index=2}  

---

# Dashboard Pages Overview

The dashboard contains multiple interactive pages designed for layered analysis.

## Page 1: Executive Summary

Provides a high-level overview of student performance.

Includes:

- KPI cards
- Completion rate
- Performance distribution
- Trend charts

Purpose:

Allows stakeholders to quickly assess overall program performance.

---

## Page 2: Analytical Deep Dive

Explores relationships between student demographics and academic performance.

Includes:

- Scatter plots
- Bar charts
- Matrix tables

Purpose:

Supports detailed demographic and academic analysis.

---

## Page 3: Engagement & Geographic Analysis

Analyzes student activity and location-based patterns.

Includes:

- Engagement trend charts
- Geographic maps
- Activity distributions

Purpose:

Identifies engagement trends across regions.

---

## Page 4: Drill-Through & Intervention Planning

Provides detailed analysis at individual student level.

Includes:

- Drill-through tables
- Scenario analysis
- Student-level metrics

Purpose:

Supports personalized intervention planning.

---

## Page 5: Predictive Insights

Uses AI-powered tools to identify performance drivers.

Includes:

- Key Influencers visualization
- Risk pattern detection

Purpose:

Supports predictive decision-making and early risk detection. :contentReference[oaicite:3]{index=3}  

---

# Key Insights

The analysis produced several critical findings:

## Demographic Insights

- Older students consistently outperform younger students.
- Students with higher prior education levels achieve better outcomes.
- Socio-economic background influences engagement patterns.

---

## Academic Insights

- Students taking excessive credit loads show lower performance.
- Balanced workloads correlate with improved academic results.
- Assessment scores gradually decline across the module timeline.

---

## Engagement Insights

- Early engagement strongly predicts success.
- Students interacting before the module start perform significantly better.
- Irregular engagement increases withdrawal risk.

---

## At-Risk Indicators

Students most likely to fail or withdraw include:

- Students with late submissions
- Students with low early engagement
- Students with limited prior education

These insights enable institutions to identify struggling students early and provide targeted support. :contentReference[oaicite:4]{index=4}  

---

# Strategic Recommendations

Based on the findings, the following strategies are recommended:

## 1. Early Warning Systems

Identify students showing:

- Low engagement
- Low assessment scores

Implement automated alerts for early intervention.

---

## 2. Targeted Support Programs

Provide academic support for:

- Students with lower education levels
- Students with poor early performance

---

## 3. Engagement Incentives

Encourage early participation through:

- Pre-module orientation
- Interactive learning tools

---

## 4. Workload Management

Advise students against excessive credit loads.

Introduce recommended limits based on performance data.

---

## 5. Continuous Monitoring

Deploy real-time dashboards to:

- Track engagement patterns
- Detect risk indicators
- Support informed decision-making

These recommendations aim to improve student retention and overall academic success. :contentReference[oaicite:5]{index=5}  

---

# Power BI Public Link

Access the live dashboard here:

https://app.powerbi.com/view?r=eyJrIjoiZWI4NDAzYmItODk3Zi00ODRmLWExMjUtY2U2NjJlYzY2MGFkIiwidCI6IjE2ZDgzZWU2LTI1NGEtNDY5ZC1hNmNjLTU0ZTJjYTIzMTNlNyIsImMiOjh9
---

# Team Members (Group F)
Hope Kimandi — Data Cleaning & Transformation  
Faith Mwangi — Data Cleaning & Transformation

Halima Mohamed — Data Modeling   
Wilson Muhia — DAX Measures Development 

Fortune Nawate — Dashboard Development  
Yar Deng Kuot — Readme   
---














