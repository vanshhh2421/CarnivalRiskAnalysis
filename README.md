# 🎪 Carnival Risk Analytics – Optimized LightGBM Pipeline

This project builds a high-performance Machine Learning pipeline to predict Insurance Premium Amounts for 1.2M+ customers using demographic, lifestyle, and financial attributes.

The pipeline is fully modular, scalable, and optimized for deployment or Kaggle-style competitions.


---

# 🚀 Key Features

✅ 1. Complete Preprocessing Pipeline

Handles missing values

One-hot encodes categorical variables

Extracts date-based features (month, year, quarter, weekday, weekend indicator)

Automatically separates numerical vs categorical columns


✅ 2. Train/Validation Split

Robust 80/20 split using train_test_split

Drops rows with missing target values


✅ 3. Optimized LightGBM Model

Uses L1 regression objective (robust to outliers)

Hyperparameters tuned for improved RMSE

Early stopping for efficient training

Category-aware LightGBM training


✅ 4. Performance Metrics

Computes RMSE on the validation set

Tracks training time



---

# 📂 Project Structure

├── train.csv
├── notebook.py / model.py
├── README.md
└── requirements.txt


---

# 🧠 Technologies Used

Python

Pandas, NumPy

Scikit-Learn

LightGBM

Matplotlib, Seaborn

GC (Garbage Collection) for memory optimization



---

# ⚙️ How the Pipeline Works

1. Import Libraries

Installs and loads required ML and preprocessing libraries.

2. Load Dataset (train.csv)

Reads customer policy data.

3. Feature Engineering

Extracts:

start_year

start_month

start_dayofweek

start_quarter

is_weekend


Removes ID and unwanted columns.

4. Preprocessing

Numerical → Median imputation

Categorical → Most frequent + One-Hot Encoding

Combines using ColumnTransformer


5. Train/Validation Split

train_test_split(test_size=0.2, random_state=42)

6. Transform Data for LightGBM

Creates dense DataFrames with correct column names and category dtype for OHE outputs.

7. Train LightGBM

With:

n_estimators=2500

learning_rate=0.05

num_leaves=128

bagging_fraction=0.95

Early stopping 100 rounds


8. Evaluate Model

Prints:

RMSE Score

Training Time



---

# 📈 Sample Output

✓ Data split into training and validation sets.
✓ Data processed and converted.
⚡ Training Optimized LightGBM Regressor...

✓ RMSE:  ___
✓ Training Time: ___ minutes
🎯 Optimized Pipeline Completed Successfully!

(Results vary depending on dataset.)


---

# 🗂️ Future Improvements

Add feature importance plotting

Hyperparameter tuning with Optuna

Add a prediction API using FastAPI

Train on full dataset and export model


