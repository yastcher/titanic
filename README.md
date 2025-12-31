# Titanic - Machine Learning from Disaster

Kaggle Getting Started competition: https://www.kaggle.com/competitions/titanic

## Results

| Submission | CV Score | Kaggle Score | Description |
|------------|----------|--------------|-------------|
| RF + features | 0.8283 | **0.78229** | RandomForest + Title, FamilySize |
| Base RF | — | 0.77033 | RandomForest, 7 base features |
| XGBoost tuned | 0.8451 | 0.76794 | GridSearch best params |
| XGBoost | 0.8361 | 0.76794 | Default params |
| LightGBM | 0.8350 | 0.76315 | Default params |

**Best:** RandomForest with feature engineering (0.78229)

**Lesson:** Higher CV score doesn't guarantee better Kaggle score. Simple RF beat tuned XGBoost.

## Features

Base: Pclass, Sex, Age, SibSp, Parch, Fare, Embarked

Engineered:
- **Title** — extracted from Name (Mr, Mrs, Miss, Master, Rare)
- **FamilySize** — SibSp + Parch + 1
- **IsAlone** — 1 if FamilySize == 1

## Setup

```bash
uv sync
uv run jupyter lab
```

## Files

```
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── gender_submission.csv
├── titanic.ipynb              # Main notebook (RF) ← best result
├── titanic_boosting.ipynb     # XGBoost & LightGBM comparison
├── titanic_gridsearch.ipynb   # XGBoost with GridSearch
├── submission.csv             # Best submission (0.78229)
├── submission_xgb.csv
├── submission_xgb_tuned.csv
├── submission_lgbm.csv
└── pyproject.toml
```
