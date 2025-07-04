# Bank Term Deposit Subscription Prediction

## Problem Statement
The goal of this project is to predict whether a bank customer will subscribe to a term deposit based on personal, financial, and campaign-related features collected through direct marketing campaigns.

## Dataset Overview
- **Dataset**: Bank Marketing Dataset (Portuguese bank)  
- **Records**: 45,211  
- **Features**: 17  
- **Target Variable**: `y` → Subscription Status (`yes` / `no`)

## Tools & Technologies
- Python  
- Pandas, NumPy  
- Scikit-learn  
- XGBoost  
- Matplotlib, Seaborn  
- SMOTE (imbalanced-learn)

## Exploratory Data Analysis (EDA)
- Studied distributions of both categorical and numerical features  
- Visualized outliers using boxplots  
- Used a correlation heatmap to understand feature relationships  
- Found a significant class imbalance: ~88% no, ~12% yes

## Data Preprocessing
- No missing values in the dataset  
- Applied label encoding for binary features  
- Used one-hot encoding for multi-class categorical variables  
- Scaled numerical features with StandardScaler  
- Used SMOTE to balance class distribution

## Models Used
- Logistic Regression  
- Decision Tree  
- Random Forest (with GridSearchCV)  
- XGBoost (with class imbalance handling via `scale_pos_weight`)

## Model Evaluation
Among the models tested, **XGBoost** achieved the highest recall (0.85), which is crucial for identifying potential customers who would subscribe.  
However, **Random Forest** had the best balance overall, with an F1-score of 0.59.

Summary:
- Logistic Regression: Good accuracy (89%) but low recall (0.33)  
- Decision Tree: Slightly lower accuracy, recall around 0.40  
- Random Forest: High recall (0.71), best F1-score (0.59)  
- XGBoost: Top recall (0.85), suitable for reducing false negatives

## Key Insights
- **Call duration** was the most important feature (46% importance)  
- Customers who had previously subscribed (`poutcome_success`) were more likely to subscribe again  
- Features like `balance`, `housing loan`, and `age` also contributed to outcomes

## Future Improvements
- Hyperparameter tuning for XGBoost and Random Forest  
- Deployment via Streamlit  
- Cost-sensitive classification for business optimization

## Project Structure
- `Banking_Business_Call_Centre_Domain.ipynb` – Main notebook  
- `banking_project.pptx` – Presentation file  
- `bank_data.csv` – Dataset used (if uploaded)

