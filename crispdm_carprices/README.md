## Used Car Price Prediction (CRISP‑DM Project)

This project applies the CRISP‑DM framework to analyze a large used‑car dataset and build a model that helps used‑car dealerships make smarter inventory and pricing decisions. The goal is to understand what drives used‑car prices and develop a reliable prediction model.

**Overview**

We worked with ~400K used‑car listings containing details such as age, mileage, condition, manufacturer, model, body type, fuel type, and price. After cleaning and engineering features, we tested multiple regression models and selected the best performer.

### CRISP‑DM Summary

**Business Understanding**

Dealerships need consistent, data‑driven pricing and better insight into which vehicles hold value.  
Objective: identify key price drivers and build a model that predicts used‑car prices accurately.

**Data Understanding and Preparation**

- Cleaned manufacturer/model inconsistencies
- Removed outliers and corrupted records
- Engineered features (age, miles per year, numeric condition, combined body type)
- Scaled numeric features and one‑hot encoded categorical variables

**Modeling**
Models tested:
- Linear Regression
- Ridge Regression
- Lasso Regression
- Polynomial degrees (1, 2, 3)

**Final Model**: Ridge Regression with degree‑2 polynomial features
**Performance**: R² ≈ 0.76–0.77

### Evaluation
- Ridge provided the best balance of accuracy and stability
- Polynomial degree‑2 improved performance without excessive complexity
- Residuals showed no major unexplained patterns

### Deployment
The final model is packaged as a scikit‑learn pipeline and can be used for:
- Pricing inventory
- Trade‑in valuation
- Market comparison
- Inventory appraisal

### Key Insights for Dealerships
**Top Price Drivers**
- **Manufacturer & Model** like Eurovan, Lexus, Land Cruiser, along with many vans, campers, and wagons retain strong value
- **Age** — Newer vehicles retain higher value
- **Mileage** — Lower mileage strongly increases price
- **Miles per Year** — Light usage boosts value
- **Condition** — Higher condition ratings significantly raise price
- **Body Type** — SUVs and trucks outperform sedans and coupes
- **Fuel Type** — Hybrids/EVs show higher median prices


### Recommendations
**Buy:**
- Late‑model vehicles
- <60K miles
- SUVs, Vans, trucks and wagons
- Top performer models along with mainstream vehicles
- Hybrids/EVs only where demand is strong

**Avoid:**
- High‑mileage sedans
- Fair/salvage condition vehicles
- Rare or niche models with low demand

**Recondition:**
- Vehicles close to “excellent” condition
- Cosmetic improvements that raise condition tier

### Tech Stack
Python, Pandas, NumPy, Scikit‑learn, Matplotlib, Seaborn, Jupyter Notebook


