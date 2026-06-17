# Concrete Compressive Strength Prediction Using Machine Learning

## Scientific Question

Can concrete compressive strength be predicted from mixture composition and curing age using machine learning models validated with GroupKFold cross-validation grouped by water-to-cement ratio?

---

## Dataset Source

Dataset: UCI Concrete Compressive Strength Dataset

Source:
https://archive.ics.uci.edu/dataset/165/concrete+compressive+strength

The dataset contains 1,030 concrete mixtures with measurements of:

- Cement
- Blast furnace slag
- Fly ash
- Water
- Superplasticizer
- Coarse aggregate
- Fine aggregate
- Age
- Compressive strength (MPa)

The target property is compressive strength.

---

## Environment Setup

Clone the repository:

```bash
git clone https://github.com/atalebai/concrete-compressive-strength-ml.git
cd concrete-compressive-strength-ml
```

Create the environment:

```bash
conda env create -f environment.yml
conda activate concrete-ml
```

Launch Jupyter Lab:

```bash
jupyter lab
```

---

## Notebook Order

Run notebooks in the following order:

1. `01_data_acquisition.ipynb`
   - Load and clean raw dataset
   - Create engineered features

2. `02_eda_featurization.ipynb`
   - Exploratory data analysis
   - Correlation analysis
   - Feature engineering evaluation

3. `03_modeling.ipynb`
   - Ridge, Lasso, and Random Forest models
   - GroupKFold cross-validation
   - Feature importance analysis

4. `04_results_visualization.ipynb`
   - Final figures
   - Model comparison plots
   - Results summary

---

## Key Results

- Dataset size: 1,030 concrete mixtures
- Engineered features:
  - Water-to-cement ratio (`w_c_ratio`)
  - Logarithmic curing age (`log_age`)
- Validation strategy:
  - 5-fold GroupKFold grouped by water-to-cement ratio deciles
- Best model:
  - Lasso Regression
  - MAE ≈ 5.90 MPa
  - R² ≈ 0.73

Major findings:

- Water-to-cement ratio is the most important predictor of compressive strength.
- Log(age) substantially improves Ridge model performance.
- Lasso retains both the engineered ratio and raw composition variables, indicating that each contributes useful information.

---

## Example Figure

Insert one figure from Notebook 4 here (Model Comparison or Feature Importance).

![Feature Importance](figures/feature_importance.png)

