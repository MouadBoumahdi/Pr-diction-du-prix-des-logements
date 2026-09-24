# House price prediction

## Goal

Estimate a house's `SalePrice` from its characteristics. The project uses the house-prices dataset supplied for the assignment.

The supplied CSV has 2,919 rows and 81 columns. All rows contain a `SalePrice`, but the last 1,459 prices have decimal values while the first 1,460 are whole numbers. This suggests the later values may be generated predictions. Their source must be confirmed before using them as training or evaluation labels. For now, use rows with `Id` 1–1460 as a provisional labeled set.

## Project structure

```text
prediction-prix/
├── data/
│   ├── raw/
│   │   └── House_Prices.csv   # original dataset; keep it unchanged
│   └── processed/
│       └── House_Prices_features.csv  # four new house columns from Step 3
├── notebooks/             # exploration, charts, and explanations
├── src/                   # reusable preparation and training code
├── models/                # trained model saved later
├── dashboard/             # Streamlit prediction app later
├── tests/                 # small checks if needed
└── README.md              # project guide and progress
```

## Progress

- [x] Create the project structure and locate the dataset.
- [x] Inspect the data, identify possible label issues, and identify `X` (house characteristics) and `y` (`SalePrice`). See `notebooks/01_etape_1.ipynb`.
- [ ] Confirm the source of prices for rows with `Id` 1461–2919.
- [x] Complete Step 1 in the beginner-friendly notebook: inspect structure and types, missing values, duplicates, inconsistent and unusual values, and `SalePrice`; choose six clear input columns for `X` and keep `SalePrice` as `y`; split the data; fill missing values, encode text, and scale numeric columns using training information only.
- [x] Make six EDA charts with Pandas, Matplotlib, and Seaborn, with a short interpretation after each chart. See `notebooks/02_eda_visualisation.ipynb`.
- [x] Create and check four extra features: total area, total bathrooms, house age, and years since renovation. See `notebooks/03_feature_engineering.ipynb`.
- [ ] Train and compare at least three regression models.
- [ ] Use cross-validation and tune one model with `GridSearchCV`.
- [ ] Evaluate with MAE, RMSE, and R²; inspect large errors.
- [ ] Explain which features influence predictions.
- [ ] Save the chosen model and build the Streamlit form.
- [ ] Add Docker setup and final run instructions.

## Key rule

Split the data into training and test sets before learning medians, categories, or scaling values. The Step 1 notebook shows this in small Pandas steps. When training models and doing cross-validation, put the same preparation inside a scikit-learn `Pipeline` so every fold learns only from its own training data.

The first notebook now contains executed inspection and preparation code. The trained model, app, and Docker setup will be added in later steps.
