# Student Performance & Retention Analytics Project

## Project Overview

This repository presents a comprehensive Power BI–based analytical solution developed by **Group F** using the **Open University Learning Analytics Dataset (OULAD)**. The dataset contains detailed records of student demographics, virtual learning environment (VLE) interactions, and academic assessments collected from distance-learning courses.

The original dataset includes over **32,000 students** and more than **10.6 million interaction records** from the virtual learning platform. For this project, a filtered cohort of approximately **29,000 students** was used to focus the analysis on meaningful academic patterns and retention behaviors.

The project aims to identify the **demographic, behavioral, and academic drivers of student success**, while supporting institutional decision-making through data-driven insights.

### The Challenge

Institutional data reveals a significant performance gap:

- Only **36%** of students achieve a **Pass or Distinction**
- Approximately **33%** of students **Withdraw** before completion
- A remaining proportion fail to meet required academic outcomes

This project addresses the need for **early intervention strategies** and improved academic support systems using analytical modeling and visualization.

---

# Technical Architecture & Data Modeling

The project is built using a **Star Schema architecture** designed to efficiently manage and analyze large-scale datasets consisting of over **10.6 million interaction records**.

## Star Schema Design

### Dimension Tables

- `studentInfo` — Contains student demographic attributes  
- `vle` — Stores virtual learning resource information  
- `Dim_Date` — Custom date dimension created for time intelligence  

### Fact Tables

- `studentVle` — Records student interactions with online resources  
- `studentAssessment` — Stores assessment submission and performance data  

This design ensures:

- Faster analytical queries  
- Improved data organization  
- Scalable reporting performance  

---

# ETL Process (Power Query)

The dataset underwent extensive transformation through an **Extract–Transform–Load (ETL)** pipeline consisting of more than **10 major transformations** to ensure data quality and usability.

## Key Transformations

### Data Imputation

Missing values in assessment scores and weights were replaced with **0** to prevent inaccurate calculations and maintain dataset completeness.

### Attribute Standardization

Categorical variables such as **Age Bands** and **IMD (Index of Multiple Deprivation) Bands** were converted from text ranges into numerical minimum and maximum values. This allowed the variables to be used in statistical analysis and aggregation.

### Temporal Normalization

A custom **DAX Date Table (`Dim_Date`)** was created to convert relative day values into standardized calendar dates. This enabled time-series analysis and monthly trend tracking.

### Relationship Optimization

One-to-many relationships were established between dimension and fact tables:

- `studentInfo` to `studentVle`  
- `studentInfo` to `studentAssessment`  
- `vle` to `studentVle`  

These relationships improved performance and ensured data integrity.

---

# Dashboard Insights & Business Intelligence

The Power BI dashboard was designed to answer key institutional questions through structured visualization pages.

---

## Executive Summary: Performance Monitoring

**Business Question:**  
Are institutional retention targets being met?

### Key Performance Indicators

- Pass Rate: **72%**
- Completion Rate: **36%**
- Withdrawal Rate: **33%**

### Trend Analysis

The dashboard visualizes **Average Score** alongside **Submission Volume** across time.

**Key Finding**

Scores initially average around **80**, but gradually decline as submission workload increases. This pattern closely aligns with an increase in late submissions, suggesting workload-related performance fatigue.

---

## Digital Engagement: Virtual Learning Analysis

**Business Question:**  
Which digital resources drive student success?

### Visual Components

- VLE Activity Treemap  
- Resource usage distribution  

### Observed Resource Types

- Forumng (discussion forums)  
- Subpages  
- PDF resources  

**Key Finding — Early Engagement Effect**

Students who interact with learning materials **before the module start date** demonstrate:

- Higher engagement levels  
- Lower withdrawal risk  

Early participation acts as a protective factor against attrition.

---

## Key Influencers: AI-Based Analysis

**Business Question:**  
What are the strongest predictors of student success?

Using Power BI’s **Key Influencers tool**, the analysis identified the following patterns:

### High Performance Drivers

Students categorized within the **Older age group (55+)** were found to be:

- **1.58 times more likely** to achieve high academic scores.

### Risk Drivers

Students at highest academic risk included:

- Students with **No Formal Qualifications**  
- Students attempting **450 or more credits**

These groups demonstrated significantly higher withdrawal likelihood.

---

## Drill-Through Analysis: Regional Risk Monitoring

**Business Question:**  
How can interventions be targeted geographically?

A dedicated regional drill-through page focuses on the **East Anglian Region**, allowing advisors to:

- Identify individual student IDs  
- Review credit loads  
- Monitor engagement scores  

This enables targeted academic interventions at a localized level.

---

# Advanced DAX Measures

Several custom DAX measures were developed to support dynamic analysis and predictive insights.

## Core Measures

### At-Risk Flag

This measure identifies students who meet both conditions:

- Average Score < 40  
- VLE Clicks < 100  

These students are flagged as high-risk candidates requiring intervention.

---

### Success Likelihood

This AI-based metric estimates the probability of achieving high academic performance using demographic and behavioral indicators.

---

### What-If Scenario Analysis

A dynamic parameter was created to simulate improvements in retention performance.

Simulation Range:

- **5% to 15% retention improvement**

This feature supports strategic planning and policy simulation.

---

# Strategic Recommendations

Based on the analytical findings, the following institutional strategies are recommended:

## Workload Management

Introduce a **credit load soft cap**:

- Recommended maximum: **300 credits**
- Mandatory counseling for students exceeding this threshold

Purpose:

Reduce academic overload and prevent performance decline.

---

## Early Intervention Strategy

Deploy automated notifications for students who:

- Show **zero VLE activity within the first week**

Purpose:

Encourage early engagement and prevent withdrawal behavior.

---

## Equity Gap Reduction

Develop **bridging modules** for students entering without formal academic qualifications.

Purpose:

Close the approximately **30% completion gap** among underprepared students.

---

## Content Optimization

Review and optimize learning resources using engagement data.

Recommended actions:

- Remove low-engagement materials  
- Expand high-engagement content  
- Increase use of interactive forum-based learning  

---

# Technologies Used

- Power BI  
- Power Query  
- DAX (Data Analysis Expressions)  
- Excel  
- Star Schema Data Modeling  
- AI-Based Key Influencers Analysis  

---

# Project Team (Group F)

- Halima Mohamed  
- Fortune Nawate  
- Yar Deng Kuot  
- Faith Mwangi  
- Wilson Muhia  
- Hope Kimandi  

---

# Academic Context

Developed for:

United States International University–Africa (USIU Africa)  
Course: Data Visualization & Analytics  
Submission Date: April 2026  

---

# Project Impact

This project demonstrates how large-scale learning analytics can be transformed into:

- Early warning systems  
- Retention improvement strategies  
- Personalized academic support frameworks  

The analytical model developed provides a scalable foundation for data-driven academic decision-making.

