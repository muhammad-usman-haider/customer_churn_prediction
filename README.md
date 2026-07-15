# Customer Churn Prediction

**Predicting customer churn is critical for subscription and service-based businesses. This repository demonstrates end-to-end churn prediction workflows implemented with multiple ML frameworks (Scikit-Learn, TensorFlow, and PyTorch). The notebooks include data exploration, preprocessing, model training, evaluation, and tips for deployment.**

---

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Dataset](#dataset)
- [Notebooks](#notebooks)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Install](#install)
  - [Run the notebooks](#run-the-notebooks)
- [Methodology](#methodology)
- [Results & Evaluation](#results--evaluation)
- [Extending & Deployment](#extending--deployment)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

---

## Project Overview

This project shows practical approaches to predict whether a customer will churn (binary classification). It explores feature engineering, categorical handling, model selection, and evaluation using standard metrics. The goal is to provide reproducible notebooks that demonstrate best practices for a churn modeling pipeline.

---

## Repository Structure

- `customer_chern_dataset.csv` — sample dataset used in the notebooks.
- `SciketLEARN_Customer_Churn_Prediction.ipynb` — Scikit-Learn based workflow (feature processing, classical ML models).
- `tensorFlow_Customer_Churn_Prediction.ipynb` — TensorFlow / Keras model implementation.
- `PYTORCH_Customer_Churn_Prediction.ipynb` — PyTorch-based model and training loop.
- `LICENSE` — project license.
- `README.md` — this file.

---

## Dataset

Filename: `customer_chern_dataset.csv`

Sample columns:
- `CustomerID` — unique customer identifier
- `Tenure` — months with the service
- `MonthlyCharges` — current monthly charge
- `TotalCharges` — cumulative charges
- `Contract` — contract type (e.g., Month-to-month, One year, Two year)
- `PaymentMethod` — payment type (e.g., Electronic check, Mailed check, Credit card)
- `Churn` — target (1 = churned, 0 = retained)

Note: The dataset included in this repo is a small sample. For production-ready modeling use a larger and more representative dataset and apply privacy best practices when handling customer data.

---

## Notebooks

Each notebook is a standalone workflow demonstrating the same problem solved using a different framework:

- Scikit-Learn notebook: data cleaning, encoding, model training (Logistic Regression, Random Forest, XGBoost, etc.), cross-validation, and feature importance.
- TensorFlow notebook: Keras model building, training with callbacks, and evaluation.
- PyTorch notebook: dataset/dataloader construction, model training loop, and evaluation.

Open the notebooks to follow the detailed steps, visualizations, and evaluation outputs.

---

## Getting Started...

### Prerequisites

- Python 3.8+
- Jupyter (Lab or Notebook)
- Typical Python packages used in the notebooks:
  - pandas, numpy, scikit-learn, matplotlib, seaborn
  - tensorflow (for the TensorFlow notebook)
  - torch, torchvision (for the PyTorch notebook)
  - jupyterlab or notebook
  - Optional: xgboost if used in Scikit-Learn notebook

### Install

Create a virtual environment and install packages:

```bash
python -m venv .venv
source .venv/bin/activate        # macOS / Linux
.venv\Scripts\activate           # Windows

pip install --upgrade pip
pip install jupyterlab pandas numpy scikit-learn matplotlib seaborn
# optional frameworks:
pip install tensorflow torch xgboost
```

If you'd like, I can add a `requirements.txt` with exact versions used in the notebooks.

### Run the notebooks

Start Jupyter and open the notebooks:

```bash
jupyter lab
# or
jupyter notebook
```

Open any of:
- `SciketLEARN_Customer_Churn_Prediction.ipynb`
- `tensorFlow_Customer_Churn_Prediction.ipynb`
- `PYTORCH_Customer_Churn_Prediction.ipynb`

Follow the cells top-to-bottom. If kernels fail to import a package, install the missing package in the environment and restart the kernel.

---

## Methodology

Common steps applied across notebooks:
1. Exploratory Data Analysis (EDA) — examine distributions, missing values, correlations.
2. Data cleaning — type conversions, imputation of missing values, outlier handling.
3. Feature engineering — encoding categorical variables (one-hot / ordinal / target encoding), scaling numerical features, interaction features if needed.
4. Train/Validation split — stratified split for imbalanced targets.
5. Model training using cross-validation, hyperparameter tuning (GridSearch / RandomSearch).
6. Evaluation — use metrics appropriate for classification and business needs (Accuracy, Precision, Recall, F1, ROC AUC, PR AUC).
7. Interpretability — feature importance, SHAP / partial dependence plots (optional).

---

## Results & Evaluation

Each notebook contains evaluation outputs and visualizations. For a production-ready pipeline:
- Track experiments (e.g., MLflow, Weights & Biases).
- Use cross-validation and a hold-out test set to estimate generalization performance.
- Pay attention to class imbalance; use metrics such as ROC AUC and precision/recall at chosen operating points.

---

## Extending & Deployment

Suggestions to take this project further:
- Add a more realistic dataset and stronger validation (time-based split if churn is temporal).
- Implement pipeline serialization (joblib, ONNX, TensorFlow SavedModel) and a model-serving REST API.
- Add automated tests for data schema and model outputs.
- Integrate monitoring for model drift and data quality.

---

## Contributing..

Contributions are welcome. Suggested ways to contribute:
- Improve notebooks (cleaner organization, modular functions).
- Add a `requirements.txt` or `environment.yml`.
- Provide scripts for training, evaluation, and exporting models (`train.py`, `evaluate.py`).
- Add unit tests and CI.

Please open an issue or submit a pull request with a clear description of changes.

---

## License

This repository includes a `LICENSE` file. Review the license for permitted uses.

---

## Contact

Maintainer: @muhammad-usman-haider (GitHub)
If you’d like this README committed or want additional files (requirements, CI, Dockerfile), tell me and I will add them.

---

## Acknowledgements

Inspiration and best practices from common churn modeling tutorials and ML guides. If any external datasets or learning resources are used, credit them in the notebooks.
