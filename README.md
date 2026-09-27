# Professor Effectiveness Analysis — RateMyProfessor

Statistical analysis of 70K+ professor records from RateMyProfessor, examining gender rating gaps, the hot-pepper attractiveness effect, and behavioral drivers of student-perceived effectiveness.

## Summary

- **Dataset:** RateMyProfessor — numeric ratings, qualitative metadata, and 20 behavioral teaching tags
- **Records:** ~70K professors after removing sparse/ambiguous rows (≥4 ratings required)
- **Analyses:** Hypothesis testing (Mann–Whitney U, permutation tests), logistic regression, Ridge regression
- **Key findings:** Male professors rated statistically higher (p < 0.005); hot-pepper flag positively correlates with ratings; behavioral tags (caring, amazing_lectures, inspirational) are the strongest rating predictors under Ridge regression

## Analyses

### 1. Gender Rating Gap
Mann–Whitney U test (one-sided, α = 0.005) on average rating by inferred gender. Male professors received statistically higher ratings; dispersion tested via permutation test on median absolute deviation.

### 2. Hot-Pepper Effect
Tested whether professors flagged as "hot" (pepper indicator) receive higher average ratings, controlling for gender.

### 3. Logistic Regression — Take-Again Prediction
Binary logistic regression predicting whether a professor's take-again rate exceeds 50%, using rating, difficulty, gender, online rating share, and normalized behavioral tags as features. Evaluated with ROC-AUC, F1, and a precision–recall curve.

### 4. Ridge Regression — Rating Prediction
Ridge regression on average rating using the 20 normalized behavioral tag proportions as features. Identifies which teaching behaviors most strongly predict student ratings.

## Repository Layout

```
ids_capstone.py       Full analysis pipeline (exported from Colab)
Capstone.ipynb        Notebook version
rmpCapstoneNum.csv    Numeric rating data
rmpCapstoneQual.csv   Qualitative metadata (major, university, state)
rmpCapstoneTags.csv   Behavioral teaching tag counts
```

## Tech Stack

`Python` `pandas` `NumPy` `scipy.stats` `scikit-learn` `Matplotlib`
