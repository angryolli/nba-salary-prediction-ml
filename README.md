# Predicting NBA Player Salaries Using In-Game Statistics

This project investigates whether NBA player salaries can be reliably predicted using individual in-game performance statistics. Using supervised machine learning, we analyze how player roles, scoring, defensive contributions, and playing time relate to compensation in the modern NBA.

## How to Run This Project

Follow these steps to set up a local Python environment, run the notebook, and use the correct kernel.

### 1. Create and activate the virtual environment

From the project root:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install required packages (including Jupyter + ipykernel)

With the virtual environment activated:

```bash
pip install -r requirements.txt
```

### 3. Use the correct kernel for the notebook

- In the **bottom-right status bar** in IDE, click the current Python version.
- Choose the interpreter inside the project virtualenv, for example:
  - Select another kerner
  - Python environments 
  - .venv (Python ...)    //Recommended
  - For example `/home/username/nba-salary-prediction-ml/.venv/bin/python`


After this, you can run the notebook cells and the project will use your `.venv` with all dependencies installed.


## Research Question

Can NBA player salaries be predicted accurately using only individual in-game performance statistics?

## Dataset

- Source: Kaggle – *NBA Player Stats and Salaries (2010–2025)*
- Seasons used: **2022–23, 2023–24, 2024–25**
- Final dataset size: **1,191 player-season entries**
- Target variable: Player salary (USD)

### Key preprocessing steps:
- Filtered out players below the league minimum salary
- Handled undefined shooting percentages by setting them to zero
- Removed categorical variables (team, position) from modeling
- Restricted to recent seasons to reduce salary inflation effects


## Models Used

- **Linear Regression (LR)**
  - Assumes linear relationship between performance and salary

- **Random Forest (RF)**
  - Captures complex interactions and reduces sensitivity to outliers

## Evaluation Methodology

- Data split: **80% training / 20% held-out test set**
- Model selection: **5-fold cross-validation on training set**
- Metrics:
  - Root Mean Squared Error (RMSE)
  - Coefficient of Determination (R²)

## Results

| Model | Test RMSE | Test R² |
|------|----------|---------|
| Random Forest | $5.69 million | 0.74 |

The Random Forest model significantly outperformed Linear Regression, indicating that NBA salaries are influenced by nonlinear combinations of performance metrics rather than purely linear relationships.


