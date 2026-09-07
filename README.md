# Telco Customer Churn Prediction

A reproducible notebook-based analysis to explore and predict customer churn using the Telco Customer Churn dataset (IBM). This repository contains a Jupyter Notebook that demonstrates end-to-end steps for a churn modeling experiment: data loading, cleaning, exploratory data analysis (EDA), feature engineering, model training, and evaluation.

## Dataset used

- Source (as used in the notebook): https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv

## Highlights

- Demonstrates practical data cleaning steps (e.g., converting `TotalCharges` to numeric and handling missing values).
- Performs exploratory data analysis to identify churn drivers.
- Includes feature preprocessing and baseline model training and evaluation within the notebook.

## Contents

- `Telco_Customer_Churn_Prediction (1).ipynb` — the primary Jupyter notebook with the full analysis.

## Quick start (local)

1. Clone the repository:
   ```bash
   git clone https://github.com/NishanthKamalakkannan/Telco-Customer-Churn-Prediction.git
   cd Telco-Customer-Churn-Prediction
   ```

2. Create and activate a Python virtual environment (optional but recommended):
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate    # macOS / Linux
   # .venv\Scripts\activate     # Windows
   ```

3. Install dependencies:
   ```bash
   pip install --upgrade pip
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

4. Open the notebook:
   ```bash
   jupyter notebook "Telco_Customer_Churn_Prediction (1).ipynb"
   ```
   Or open in Google Colab by uploading the notebook or opening it from the GitHub interface.

## What the notebook does (high level)

1. Loads the Telco Customer Churn CSV from the IBM-hosted raw URL.
2. Inspects dataset structure and types; identifies `TotalCharges` incorrectly loaded as object.
3. Converts `TotalCharges` to numeric, coerces non-numeric values to NaN, investigates rows with NaN (customers with tenure = 0), and handles them.
4. Drops non-informative identifier columns (e.g., `customerID`) and prepares features.
5. Performs EDA (distributions, categorical relationships vs churn).
6. Encodes categorical features and scales numeric features as needed.
7. Trains baseline models (see notebook for specific algorithms and evaluation metrics) and reports performance.

## Key findings & notes (from the notebook)

- `TotalCharges` contains values that require conversion to numeric; a small set of new customers had missing total charges which the notebook fills (or handles) before modeling.
- The notebook is a self-contained analysis suited for education, demonstration, and baseline model comparisons.

## Recommended next steps / improvements

- Add a `requirements.txt` or `environment.yml` so environments can be reproduced exactly.
- Convert the notebook's data-cleaning and modeling steps into modular Python scripts or a Python package for reuse/testability.
- Add unit tests and a CI pipeline to validate code changes.
- Persist the best model using joblib/pickle and add a small inference script or Flask/FastAPI service for deployment experiments.
- Perform hyperparameter tuning (GridSearchCV/RandomizedSearchCV) and cross-validation to stabilize model selection.
- Add model explainability (SHAP/LIME) to surface feature importances and support business decisions.

## License

Add a license file if you intend to make this project public and to specify usage terms (MIT, Apache-2.0, etc.).

## Contact / Author

Repository owner: NishanthKamalakkannan (GitHub)
