# 🚚 Dynamic Delivery ETA Prediction

Predicting package delivery times using machine learning with real-world inspired features such as distance, traffic, weather, and warehouse data.  
This end-to-end project demonstrates data cleaning, feature engineering, model training, comparison, and evaluation using modern gradient boosting algorithms.

---

## 📌 Project Overview

- **Goal:** Build a predictive model to estimate delivery duration (ETA) in minutes.  
- **Techniques Used:** Feature engineering, Gradient Boosting (XGBoost, LightGBM, CatBoost), Model Comparison, Explainability (Feature Importance).  
- **Impact:** Helps logistics teams reduce late deliveries and optimize resource planning.  
- **Results:** Achieved MAE ≈ **6.8 minutes** on validation data using CatBoost.

---

## 📊 Dataset

- **Description:** Historical delivery records with pickup/dropoff coordinates, trip durations, and timestamps.  
- **Additional Features (simulated):**  
  - Traffic level (low, medium, high)  
  - Weather (rain/no rain)  
  - Warehouse IDs  
- **Target Variable:** Delivery duration in minutes (`delivery_duration`).  

📂 **Note:** Due to size restrictions, datasets (`train.csv`, `test.csv`) are not included in this repo.   

---

## ⚙️ Feature Engineering

- **Distance:** Haversine formula for pickup → dropoff distance.  
- **Time Features:** Hour of day, weekday, month.  
- **Traffic & Weather:** Randomized proxies for congestion and rain.  
- **Warehouse ID:** Encoded warehouse assignment.  
- **Target Conversion:** Converted `trip_duration` (seconds) → `delivery_duration` (minutes).  

---

## 🏗️ Modeling

- **Data Split:** 80% training, 20% validation.  
- **Algorithms Used:**  
  - XGBoost  
  - LightGBM  
  - CatBoost  
- **Metrics:** Mean Absolute Error (MAE), Root Mean Squared Error (RMSE).  
- **Model Persistence:** Saved trained models (`.pkl`) with Joblib.  

---

## 📈 Results

**Validation Metrics:**

| Model     | MAE (minutes) | RMSE (minutes) |
|-----------|---------------|----------------|
| CatBoost  | **6.82**      | 54.93          |
| LightGBM  | 6.91          | 55.71          |
| XGBoost   | 7.04          | 60.32          |

**Feature Importance (XGBoost Example):**

![Feature Importance](outputs/feature_importance.png)

---

## 💾 Reproducibility

- Run the `Delivery_ETA_Notebook.ipynb` in **Google Colab**.  
- Mount Google Drive to access datasets and save outputs.  
- Models and results are automatically saved for future use.  

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/Delivery_ETA_Prediction.git
   cd Delivery_ETA_Prediction

