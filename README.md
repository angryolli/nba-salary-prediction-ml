# Predicting NBA Player Salaries Using In-Game Statistics

This project investigates whether NBA player salaries can be reliably predicted using individual in-game performance statistics. Using supervised machine learning, we analyze how player roles, scoring, defensive contributions, and playing time relate to compensation in the modern NBA.

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

## Conclusion

Random Forest models provide superior predictive performance for NBA salary estimation based on in-game statistics. While Linear Regression offers interpretability, it struggles with nonlinear effects and salary outliers.

