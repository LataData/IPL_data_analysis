
# IPL T20 Score Prediction Using Machine Learning

This project predicts **first-innings total scores in IPL T20 matches** using real-time match data such as overs, runs, wickets, and performance in the last 5 overs. A Random Forest regression model was trained on ball-by-ball IPL data to output accurate score predictions.

---

## Project Objective

To build a machine learning pipeline that uses in-match progress features to predict the final first-innings total in IPL matches. The goal is to support analytics platforms, fantasy games, and live commentary tools with accurate score forecasts.

---
## Libraries Used
Python (Jupyter Notebook)

pandas, numpy for data wrangling

matplotlib, seaborn for visualization

scikit-learn for model building

pickle for model saving/loading

---

##  Dataset Overview

- **Type**: IPL Ball-by-Ball Match Data  
- **Rows**: 76,014 deliveries  
- **Columns**: 15 (e.g., `bat_team`, `bowl_team`, `overs`, `runs`, `wickets`, `runs_last_5`, `wickets_last_5`, etc.)  
- **Target Variable**: `total` (final score in the first innings)  
- **No missing values**

---

##  Exploratory Data Analysis Highlights

- Run rate significantly accelerates after over 15  
- Middle overs (7–15) show highest wicket fall probability  
- Scoring 30+ runs in the last 5 overs often leads to totals above 180  
- Feature distributions were studied over seasons and match situations

---

##  Feature Engineering

- Categorical encoding: `bat_team`, `bowl_team`, `venue`
- Created `runs_last_5`, `wickets_last_5` from ball-level data
- Dropped high-cardinality fields (`batsman`, `bowler`, `striker`, etc.)
- Final features: overs, runs, wickets, recent form (last 5 overs), and team context

---

##  Model Building

Four regression models were trained and compared:

| Model                 | Relative RMSE | R² Score |
|-----------------------|----------------|----------|
| Linear Regression     | 10.32%         | 72.17%   |
| Decision Tree         | 12.88%         | 56.71%   |
| AdaBoost Regressor    | 10.51%         | 71.18%   |
| **Random Forest**     | **1.84%**      | **99.11%**  |

 **Final Model:** `Random Forest Regressor`  
 Saved using `pickle` as `ipl_score_predictor.pkl`





