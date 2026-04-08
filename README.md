# Student Performance Analysis Dashboard – OULAD

**An interactive Power BI dashboard exploring what drives student success, failure, and withdrawal in online learning, using the Open University Learning Analytics Dataset (OULAD).**

---

## The problem this solves

Over 29,000 student records show a challenging reality:

- 36% successfully complete their courses
- 33% withdraw
- 31% fail

That means nearly two out of three students are not succeeding.

This dashboard helps educators and administrators move from guessing to knowing — identifying at-risk students early and understanding which factors actually improve outcomes.

---

## Project files

| File | Description |
|------|-------------|
| `assessments.csv` | Assessment details per course |
| `courses.csv` | Course module information |
| `studentAssessment.csv` | Student scores and submission records |
| `studentInfo.csv` | Demographics, education level, final results |
| `studentRegistration.csv` | Registration and unregistration dates |
| `Model View Project.docx` | Step-by-step model design with screenshots |
| `Report.docx` | Full project report (findings and recommendations) |
| `DAX measures explanations and screenshots.docx` | All DAX formulas explained |

---

## Building the data model (step by step)

Raw data is rarely ready for analysis. Here's how we shaped it.

### 1. Raw tables – before relationships

Initially, tables were disconnected and not optimized.

![Raw model view](media/screenshot_042515.png)
*Caption: Tables exist but no meaningful relationships yet.*

### 2. Table structure overview

We worked with several core tables that needed to connect properly.

![Table structure](media/screenshot_042556.png)
*Caption: Main tables include studentInfo, studentAssessment, courses, vle, and studentVle.*

### 3. Building relationships

We added relationships to link tables logically.

![Relationships being built](media/screenshot_042714.png)
*Caption: Connecting fact tables to dimension tables.*

### 4. Final star schema model

After cleaning, we created a clean star schema.

![Final model view](media/screenshot_043145.png)
*Caption: FactStudentInfo, Dim_Date, DimCourse, and other dimension tables properly related.*

### 5. Course details example

A sample of cleaned course data.

![Courses data](media/screenshot_043114.png)
*Caption: Each course has a module code, presentation code, and module length.*

### 6. The date table – `Dim_Date`

We created a dedicated DAX date table to handle time-based analysis (trends over weeks, months, etc.), making it possible to analyze student activity before, during, and after each module.

---

## Key DAX measures (explained simply)

| Measure Type | What it does |
|--------------|---------------|
| Basic | Total students, average score |
| VLE | Total clicks, avg clicks per student |
| Assessment | Pass rate (score 40 or higher), submission rate |
| Student outcomes | Completion rate, dropout rate |
| Risk indicator | At-risk students = low engagement + low score |

Full DAX formulas and screenshots are in `DAX measures explanations and screenshots.docx`.

---

## Dashboard pages – what you can explore

The final report has 5 interactive pages. Below are real screenshots.

### Page 1: Executive Summary

High-level overview of student counts, performance distribution, and monthly trends.

![Executive summary](media/screenshot_043252.png)
*Caption: Monthly counts of assessments, at-risk students, and performance distribution.*

### Page 2: Demographics and Education

How age, gender, education level, and region affect student success.

![Demographics analysis](media/screenshot_043311.png)
*Caption: Total students by highest education and gender, average score by studied credits, and completion rate by highest education.*

### Page 3: Engagement and Geography

Student activity patterns and geographic distribution.

![Engagement and geography](media/screenshot_043409.png)
*Caption: Performance by age group, total clicks by activity type, completion rate by gender, and geographic distribution.*

### Page 4: Key Influencers – What really drives success?

Power BI automatically identifies which factors most strongly predict high performance.

![Key influencers](media/screenshot_043214.png)
*Caption: Key influencers showing that older age, late module activity, and activity before module start all increase likelihood of high performance.*

**Top influencers for high performance:**

| Factor | Impact |
|--------|--------|
| Age category = Older | 1.58x more likely |
| Activity period = Late module | 1.29x more likely |
| Activity period = Before start | 1.26x more likely |
| Disability = No | 1.23x more likely |
| Gender = Male | 1.14x more likely |
| Age category = Middle age | 1.12x more likely |

Being older, engaging early and late in the course, and having no disability are the strongest predictors of success.

### Page 5: Completion Rate Summary

A simple but powerful metric.

![Completion rate](media/screenshot_043346.png)
*Caption: Overall completion rate = 38%*

---

## Key findings (plain English)

- Older students perform significantly better – 1.58x more likely to be high performers
- Higher prior education equals higher success – post-graduate students do best
- Too many credits lowers scores – cognitive overload is real
- Activity before the module starts is a strong success predictor (1.26x)
- Late module engagement also matters (1.29x) – it's never too late to engage
- At-risk students can be identified early using low engagement plus low scores
- Regional differences exist – some regions have much larger student populations

---

## Tools and technologies

- Power BI Desktop – dashboard design and modeling
- Power Query – data cleaning and merging
- DAX – measures and calculated tables
- OULAD dataset – open learning analytics data

---

## Limitations (honest and clear)

- Click data doesn't always mean real learning (scrolling versus studying)
- No information on employment, mental health, or home environment
- Correlations, not causation
- Filtered dataset may not represent all student populations

---

## Recommendations

- Build an early warning system for at-risk students
- Provide extra support for students with low prior education
- Design courses to encourage pre-course engagement
- Monitor late-module activity as a positive sign, not just early activity
- Limit course overload automatically
- Use live dashboards instead of semester-end reports

---

## Final thoughts

This project proves that data can help educators act before it's too late. With the right model and metrics, you move from guessing to knowing — and from reacting to preventing.

The Key Influencers feature alone reveals a surprising insight: engagement before a course even starts is a major predictor of success. That is actionable.

If you are an educator, analyst, or student of learning analytics, feel free to use this as a template or starting point.

---

## Screenshot reference

| Screenshot | Shows |
|------------|-------|
| `screenshot_042515.png` | Raw tables before relationships |
| `screenshot_042556.png` | Table structure overview |
| `screenshot_042714.png` | Relationships being built |
| `screenshot_043114.png` | Courses data example |
| `screenshot_043145.png` | Final star schema model |
| `screenshot_043214.png` | Key influencers (most important) |
| `screenshot_043252.png` | Executive summary dashboard |
| `screenshot_043311.png` | Demographics and education page |
| `screenshot_043346.png` | Completion rate summary |
| `screenshot_043409.png` | Engagement and geography page |

---
