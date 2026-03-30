# AIRMAN Data Science Assessment Report (Student Risk Prediction System)

---

## Problem Overview:

- The goal of this project is to predict student risk levels (on_track, needs_attention, critical) based on engagement and performance data.

- The objective is not just prediction, but to help instructors identify at-risk students early and take action.

---

## Approach:

### Data:

- Since the dataset was not provided, a synthetic dataset was created to simulate student behavior, including:
  - attendance
  - quiz performance
  - activity levels
  - missed sessions
  - submission patterns

- These features help capture student engagement, consistency, and academic performance.
- The model performance is optimistic and not representative of real-world generalization.
- In a real scenario, we would use historical real outcomes instead.

---

### Data Understanding and Cleaning:

- Checked dataset shape and structure
- Verified data types of all features
- No major missing values observed
- No duplicate records found
- Data was consistent and suitable for modeling

---

### Exploratory Data Analysis (EDA):

- EDA was performed to understand patterns in student performance.

- EDA showed that:
  - Attendance and quiz scores are strong indicators of performance
  - Higher inactivity (days since last activity) is linked to higher risk
  - No single feature explains outcomes — multiple factors contribute

---

### Modeling:

- Two models were used:
  - Logistic Regression (baseline)
  - Random Forest (final improved model)

- Random Forest was selected because it captures non-linear patterns and performs better.

---

## Model Performance:

- Logistic Regression: ~57% accuracy  
- Random Forest: ~85% accuracy  

- The Random Forest model significantly improves performance across all classes.

---

## Key Insights:

- Students with low attendance, low quiz scores, and high inactivity are more likely to be at risk  
- The model performs best for on_track students  
- Most confusion occurs between needs_attention and critical  

---

## Error Analysis:

- False negatives for critical students are the most important errors  
- Missing high-risk students can delay intervention  
- Model performance is consistent across batch groups  

---

## Business Interpretation:

- The model should be used as a **decision-support tool**, not an automated system.

- Students can be grouped into:
  - Critical → immediate intervention  
  - Needs Attention → monitoring  
  - On Track → no action required  

---

## Product Output:

The output includes:
- student_id
- risk_label (on_track / needs_attention / critical)
- risk_score (0–100)  
- top 3 contributing factors  
- recommended actions  

Output Format:
- The output is saved as:
  - CSV file (`Student_Risk_Output.csv`)
  - JSON file (`Student_Risk_Output.json`)

Example Output (JSON):

```json
{
    "student_id":"STD_094",
    "risk_label":"critical",
    "risk_score":77,
    "top_factors":[
      "High inactivity",
      "Low attendance",
      "Low quiz score"
    ],
    "recommendation":"Take immediate action: schedule instructor review and provide extra support."
  }
```

---

## Product Application:

This allows instructors to:
- prioritize high-risk students  
- understand why a student is at risk  
- take targeted actions  

---

## Limitations:

- Dataset is synthetic, so results may not reflect real-world performance  
- The target variable was synthetically generated using feature-based rules, which may introduce label leakage. As a result, model performance may be optimistic and not fully representative of real-world scenarios.
- Model may still confuse between medium-risk and high-risk students  
- Limited features

---

## Improvements:

- Use real-world data  
- Improve feature engineering  
- Tune model hyperparameters  
- Improve recall for critical students  
- Add fairness/bias evaluation  

---

## Conclusion:

- The model provides a useful way to identify at-risk students and support intervention decisions.

- Focusing on reducing errors for critical students is the most important next step.

- The model is most valuable when used alongside human judgment.

- Overall, this solution helps AIRMAN proactively identify and support students at risk, improving decision-making and academic success.

---


