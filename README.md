#  Calorie Burn Prediction Using Machine Learning

This project builds a regression model to predict **calories burned** during physical activity using biometric and workout-related data. It leverages two datasets: one with exercise session details and another with calorie expenditure. The goal is to help individuals or fitness platforms estimate energy expenditure based on measurable parameters.

---

## 📁 Datasets

### 1. `exercise.csv`

This dataset includes detailed information on users and their workouts:

* `User_ID`
* `Gender`
* `Age`
* `Height` (cm)
* `Weight` (kg)
* `Duration` (minutes)
* `Heart_Rate` (bpm)
* `Body_Temp` (°C)

### 2. `calories.csv`

This file contains the calorie expenditure corresponding to each `User_ID` entry:

* `User_ID`
* `Calories` (target variable)

> These two datasets are merged on the `User_ID` column to build the modeling dataset.

---

## 🔍 Workflow

1. **Data Merging**

   * Combine `exercise.csv` and `calories.csv` on `User_ID`.

2. **Data Cleaning & Preprocessing**

   * Drop `User_ID` as it’s not predictive.
   * Check for and handle missing values.
   * Encode categorical data (`Gender`) using one-hot encoding.
   * Separate features into numerical and categorical subsets.
   * Merge the cleaned and encoded features into a single DataFrame.

3. **Exploratory Data Analysis (EDA)**

   * Use distribution plots and boxplots to analyze feature distributions and detect outliers.
   * Correlation heatmaps to identify relationships between features and the target (`Calories`).

4. **Model Training & Evaluation**

   * Split the dataset into training and testing subsets (80/20).
   * Train multiple regression models:

     * Linear Regression
     * Random Forest Regressor
     * Decision Tree Regressor
     * XGBoost Regressor
   * Evaluate performance using:

     * R² Score
     * MAE (Mean Absolute Error)
     * MSE & RMSE (Root Mean Squared Error)

5. **Result Visualization & Model Interpretation**

   * Plot distribution of residuals (errors).
   * Feature importance visualization (for tree-based models).
   * Compare model performance.

---

## 🧠 Technologies

* Python 3 (Jupyter Notebook)
* Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost

---

## 🚀 How to Run

1. Clone this repository:

```bash
git clone https://github.com/yourusername/calorie-burn-prediction.git
cd calorie-burn-prediction
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Launch the notebook:

```bash
jupyter notebook Calories_Burnt_Prediction.ipynb
```

---

## 📌 Future Enhancements

* Deploy the best model using **Streamlit** or **Flask** for web app integration.
* Add real-time prediction input interface for user convenience.
* Enhance the dataset with wearable device metrics (steps, activity type, etc.) for greater accuracy.
* Implement automated hyperparameter tuning and cross-validation pipeline.

---

## 📊 Key Insights

* Calorie burn is highly correlated with duration, weight, and heart rate.
* XGBoost performed best with a high R² score (\~0.996), and lowest MAE and RMSE.
* Visual EDA helped in detecting outliers and skewed distributions, informing better preprocessing.

---

*This project demonstrates how machine learning can support fitness and health analytics with scalable predictions based on biometric inputs.*
