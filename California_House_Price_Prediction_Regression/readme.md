# California Housing Price Prediction
![image](https://github.com/user-attachments/assets/ba9a6e4c-778c-4381-870d-46f2f2fda24f)


## 📌 Project Overview
This project involves building predictive models to estimate California housing prices based on various features such as median income, total rooms, population, and more. The dataset is sourced from Kaggle's California housing dataset.

## 📊 Dataset Information
The dataset consists of the following features:
- **longitude, latitude**: Geographic coordinates of the house.
- **housing_median_age**: Age of the house.
- **total_rooms, total_bedrooms**: Count of rooms and bedrooms in the house.
- **population**: Population in the housing block.
- **households**: Number of households in the block.
- **median_income**: Median income of residents.
- **median_house_value**: Target variable (house price).

### **Feature Engineering**
Three additional features were derived to improve model performance:
- `rooms_per_person = total_rooms / population`
- `population_per_household = population / households`
- `bedrooms_per_room = total_bedrooms / total_rooms`

## 🏗 Model Development
We implemented multiple models to predict housing prices:
1. **Ordinary Least Squares (OLS) Regression** – To analyze feature significance.
2. **Random Forest Regressor** – A tree-based ensemble model.
3. **XGBoost Regressor** – A gradient-boosting model.

## 🔧 Hyperparameter Tuning
Minimal tuning was performed using `RandomizedSearchCV` for optimal model selection. The parameters tuned include:
- **RandomForestRegressor**: `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`
- **XGBRegressor**: `n_estimators`, `learning_rate`, `max_depth`, `subsample`, `colsample_bytree`

## 📈 Model Performance Comparison
| Model                         | MAE     | RMSE      | R² Score |
|--------------------------------|---------|-----------|----------|
| **OLS Regression**             | -       | 67060.45  | 0.6736   |
| **Random Forest Regressor**    | 32657.06 | 50634.75  | 0.80     |
| **XGBoost Regressor**          | 31395.37 | 48232.78  | 0.82     |
| **Optimized Random Forest**    | 32591.44 | 50637.23  | 0.80     |
| **Optimized XGBoost**          | 30664.60 | 47049.60  | 0.83     |

### **Key Observations**
- XGBoost outperforms all models with the highest R² score (0.83) and lowest RMSE (47,049.60).
- Feature engineering improved performance.
- Hyperparameter tuning provided marginal improvements, mainly benefiting XGBoost.


## 🏆 Conclusion
This project demonstrates the effectiveness of ensemble learning in predicting housing prices. XGBoost emerged as the best-performing model, making it a strong candidate for production deployment.

---
📌 **Next Steps:** Feature selection improvements, additional tuning, and deep learning models.


