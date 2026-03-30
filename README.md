# AIRMAN Data Science Assessment (Student Risk Prediction System)

## Overview
This project predicts student risk levels (on_track, needs_attention, critical) using a Random Forest model to help identify students who may need intervention.

## Dataset
The dataset contains student activity and performance data, including:
- attendance  
- quiz scores  
- engagement metrics  

## 1. What is implemented:
- End-to-end student risk prediction system  
- Exploratory Data Analysis (EDA)  
- Models:
  - Logistic Regression (baseline)  
  - Random Forest (final model)  
- Evaluation using accuracy, precision, recall, F1-score, confusion matrix  
- Feature importance analysis  
- Product layer with: risk_label, risk_score, top factors, and recommendations  

## 2. How to run:
1. Install requirements: 
```
   pip install -r requirements.txt
```

2. Run notebook:
```
   Airman_Data_Science_Assessment.ipynb
```

## 3. Dataset assumptions:
- Synthetic dataset (no missing values)  
- Designed to simulate real student behavior  
- Results are indicative, not real-world  
- Since the target was created using the same features, the model may be learning those patterns, so performance might be slightly better than real-world.

## 4. Model/scoring approach:
- Logistic Regression as baseline
- Random Forest selected as final model  
- Accuracy ≈ 85%  
- Risk score = probability of "critical" (0–100)  

## 5. Evaluation summary:
- Strong overall performance  
- Model performs well with accuracy ≈ 85%  
- Good detection of critical students  
- False negatives are most important → prioritize recall  

## 6. How AIRMAN could use this:
- Rank students by risk score  
- Show risk level, key factors, and recommendations  
- Helps instructor identify at-risk students early 
- Supports decision-making for timely interventions

## 7. AI tools used:
- ChatGPT (used for explanation of concepts; all implementation and decisions were independently verified)

## 8. What you would improve next:
- Use real-world data  
- Improve feature engineering and tuning  
- Add bias/fairness checks  
- Improve recall for critical students  

## 9. Output:
- See Student_Risk_Output.csv
- See Student_Risk_Output.json
