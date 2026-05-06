## Diamond Price Prediction Engine: High-Precision Valuation using XGBoost

### Project Overview
This project focuses on predicting the market price of diamonds based on their physical attributes, commonly known as the "4 Cs." Utilizing XGBoost Regression, the developed model provides highly accurate gemstone appraisals to support data-driven decision-making within the jewelry and gemstone industries.

---

### Performance Metrics
*   **$R^2$ Score:** 0.9821 (The model accounts for 98.2% of the variance in diamond prices).
*   **Mean Absolute Error (MAE):** $263.33 (The average deviation between predicted and actual market prices).

---

### Data Science Pipeline
The project follows a structured, end-to-end workflow designed for robustness and production readiness:

*   **Data Cleaning and Imputation:** Missing numerical values were addressed using Mean Imputation to ensure dataset consistency.
*   **Ordinal Encoding:** Categorical quality grades—including Cut, Color, and Clarity—were mapped to a ranked numerical scale to maintain the logical value hierarchy inherent in diamond grading.
*   **Log Transformation:** The target price variable was processed using `np.log1p` to normalize skewed distributions and more accurately capture exponential price increases relative to size.
*   **Hyperparameter Tuning:** The XGBoost regressor was optimized via `RandomizedSearchCV`, evaluating 30 distinct combinations of learning rates, tree depths, and estimators to identify the highest-performing configuration.
*   **Evaluation and Diagnostics:** Residual Analysis and Feature Importance plots were utilized to identify potential model biases and isolate primary price drivers.

---

### Key Insights
*   **Primary Drivers:** Carat weight was identified as the most significant predictor of price, followed by physical dimensions (length, width, and depth).
*   **Statistical Optimization:** Implementing log-transformation proved critical for reducing error margins, particularly when valuing high-value and rare gemstones.

---

### Technical Stack
*   **Language:** Python
*   **Libraries:** Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn
*   **Model Persistence:** Joblib

---

### Project Structure
*   **`diamonds.csv`:** The source dataset containing diamond attributes and historical pricing.
*   **`diamond_analysis.py`:** The primary Python script containing the complete data processing and modeling pipeline.
*   **`diamond_price_model.pkl`:** The final serialized model, optimized and ready for deployment.
