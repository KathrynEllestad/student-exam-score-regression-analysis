# Modeling Exam Scores Using Regression Analysis

## Project Overview

This project examines which behavioral, environmental, and parental factors are most strongly associated with student exam performance. Using a large synthetic dataset of student characteristics and outcomes, the analysis applies multiple linear regression to identify key predictors, evaluate model assumptions, and assess whether increased model complexity improves predictive performance.

The goal of the project is to demonstrate rigorous statistical modeling practices, including variable selection, diagnostics, outlier analysis, and model validation, while maintaining interpretability and practical relevance for educational decision-making.

---

## Research Questions

This analysis was guided by the following questions:

- Which factors have the strongest relationship with student exam scores?
- Do behavioral, environmental, and parental predictors remain significant when evaluated together?
- Do interaction terms or nonlinear effects meaningfully improve prediction accuracy?
- Are there outliers or influential observations affecting model results?

---

## Data Description

- **Observations:** 6,607 students  
- **Response Variable:**  
  - Exam Score (percentage)
- **Predictors:**  
  - Behavioral: hours studied, attendance, sleep hours, previous exam scores, physical activity  
  - Support-related: tutoring sessions, parental involvement, access to resources, parental education  
  - Contextual: income level, internet access, school type, learning disabilities, peer influence  

The dataset is synthetic and was created for analytical and educational purposes. While it does not represent real students, it reflects realistic distributions and relationships commonly observed in educational data.

---

## Methods

### Exploratory Data Analysis (EDA)

- Exam scores exhibited an approximately normal distribution, supporting the use of linear regression.
- Attendance, hours studied, and previous exam scores showed the strongest positive relationships with exam performance.
- Several predictors (e.g., sleep hours, physical activity) displayed weaker or noisier patterns.

---

### Model Development

Three regression models were evaluated:

1. **Main-Effects Linear Model**  
   - Predictors: hours studied, attendance, previous exam scores, tutoring sessions, parental involvement, access to resources  
   - Selected using stepwise regression and all-possible-models comparison to balance fit and parsimony

2. **Two-Way Interaction Model**  
   - Added all first-order interaction terms  
   - Did not meaningfully improve fit (higher MSE, lower adjusted R²)

3. **Quadratic Model**  
   - Added nonlinear terms  
   - Increased complexity without improving predictive performance

Partial F-tests confirmed that neither interaction nor quadratic terms justified the additional complexity.

---

## Model Diagnostics & Validation

- Regression assumptions were evaluated using residual plots, normal quantile plots, leverage statistics, and Cook’s distance.
- A small cluster of high-performing students (approximately 0.76% of observations) was identified as outliers with large studentized residuals.
- These outliers were not influential on model coefficients but indicated a meaningful subgroup not captured by the measured predictors.
- After refitting the model without this outlier cluster:
  - Adjusted R² increased from ~0.66 to ~0.90
  - Residual normality and homoscedasticity improved substantially
- Cross-validation using an 80/20 split showed consistent model performance, indicating good generalization for the average student.

---

## Key Findings

- The strongest predictors of exam performance were:
  - Previous exam scores
  - Hours studied
  - Attendance
- Parental involvement and access to resources also contributed meaningfully, though with smaller effects.
- Interaction and nonlinear effects did not improve model performance enough to justify added complexity.
- A distinct group of high-achieving students exhibited performance beyond what the model could explain, suggesting the presence of unobserved factors such as study strategies or course difficulty.

---

## Files

- [Final Report (PDF)](report/Group_3_Report.pdf)
- [Presentation Slides (PDF)](report/Group_3_Presentation.pdf)
- [Dataset (CSV)](data/StudentPerformanceFactors.csv)
- [JMP Project File](analysis/Final_Project.jmpprj)

---

## Tools & Methods

- Multiple linear regression
- Stepwise variable selection and all-possible-models comparison
- Regression diagnostics and assumption checking
- Outlier and influence analysis
- Cross-validation
- JMP (statistical modeling and diagnostics)

---

## Notes

This project was completed as part of a STAT 311 Regression Analysis course and reflects an end-to-end statistical modeling workflow, from exploratory analysis and model selection through diagnostics, validation, and interpretation.

While the project originated in a group course setting, the analysis, modeling decisions, and documentation presented in this repository reflect my individual work.
