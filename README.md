# assignment2

The dataset is too big to upload here, but I use the dataset of NYC 2024 DEC 31st. Rhoad Island DEC 31st. NYC 2024 Apr 6th.

# Airbnb Pricing Prediction Model

This project develops a machine learning model to predict Airbnb listing prices across different cities and time periods. The model aims to help Airbnb operators determine optimal pricing strategies by analyzing property features, location data, and market dynamics.

---

## Project Structure

### 1. Data Collection and Exploration

**Datasets:**
- NYC Main dataset (37,434 listings)
- NYC 2024 Q1 dataset (38,377 listings)
- Rhode Island dataset (5,479 listings)

**Initial Explorations:**
- Checking data shapes and consistency
- Identifying missing values
- Analyzing price distributions across cities and time

---

### 2. Data Preprocessing

**Cleaning Steps:**
- Converted price strings to numeric
- Removed price outliers (1st–99th percentile)
- Extracted host experience from registration date
- Imputed missing values (mostly median)
- Converted categorical variables to binary
- Applied log-transformation to `price`

---

### 3. Feature Engineering

**Amenities:**
- Parsed JSON-style amenities
- Created binary indicators for top 20 amenities
- Developed amenity categories (essentials, luxury, safety)
- Counted total amenities per listing

**Derived Features:**
- Person-per-bedroom ratio
- Average review scores
- One-hot encoding of room/property types
- Neighborhood clustering and encoding
- Distance to city center (km)
- Booking flexibility metrics

---

### 4. Model Building

**Preparation:**
- Removed leakage variables
- Train-test split (80/20)
- Standardized numeric features

**Models:**
- Ordinary Least Squares (OLS / Ridge)
- LASSO Regression
- Random Forest
- LightGBM (Gradient Boosting)
- k-Nearest Neighbors (KNN)

**Metrics:**
- R² (coefficient of determination)
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- Training & prediction time

---

### 5. Feature Importance Analysis

- Identified key pricing drivers in each model
- Compared importance distributions
- Grouped features by category (location, host, property)
- Found dominant features:
  - Room type in Random Forest (~25%)
  - Distance to center in LightGBM (~8%)

---

### 6. Model Validation on New Datasets

**NYC 2024 Q1 (Temporal Validation):**
- Avg performance drop: **-43.25%**

**Rhode Island (Geographic Validation):**
- Avg performance drop: **-89.34%**

**Insights:**
- Tree-based models (LightGBM, RF) had best generalization
- Linear models (OLS, LASSO) degraded heavily
- Geographic transfer harder than temporal shift

---

## Key Findings

- **LightGBM** outperformed all models (R² = 0.775)
- **Random Forest** was a close second (R² = 0.757)
- Tree-based models significantly outperformed linear methods
- **Top features:** room type, distance to center, host characteristics
- Models need retraining across different cities
- **Location & property type > amenities** in driving price

---

## Technologies Used

- Python
- pandas, NumPy
- scikit-learn
- LightGBM
- Matplotlib, Seaborn

---

## Conclusion

This project demonstrates a full pipeline for price modeling using real-world Airbnb data, with strong results and valuable insights for pricing optimization across time and space.  
It highlights the importance of using robust machine learning models and thoughtful feature engineering in dynamic markets.

---






