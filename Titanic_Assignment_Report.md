# Titanic Data Mining Assignment Report

## Goal
This project analyzes the Titanic dataset to understand which passenger characteristics were associated with survival. The objective is to identify patterns that explain why some passengers survived and others did not, while also paying attention to fairness, data quality, and interpretation.

## Data cleaning summary
The raw Titanic data contained missing values, especially in age, embarkation port, and cabin information. Age was imputed using the median age within sex and passenger class to preserve realistic variation while avoiding the distortion of a single global median. Missing embarkation values were filled using the most common port. A binary indicator for cabin presence was created, and weak identifiers such as name, ticket, and cabin were removed because they were either unhelpful or too sparse for modeling. Outliers in fare were clipped to limit the influence of unusually expensive tickets. Categorical variables such as sex, class, embarkation port, and passenger type were encoded for modeling, and numeric variables were standardized to ensure fair comparison across features.

## Main insights from the EDA
- Women had a much higher survival rate than men.
- First-class passengers had the highest survival probability, followed by second class and then third class.
- Survival varied by embarkation port, suggesting that some groups may have had distinct access to lifeboats or boarding locations.
- Age showed a nontrivial relationship with survival and therefore should be kept in the feature set after careful imputation.
- The dataset was moderately imbalanced, with approximately 38% survivors and 62% non-survivors.
- The strongest predictive signals were social and demographic variables, especially sex and class.

## Ethical and methodological reflection
The Titanic data is historical and reflects social structures from 1912, including inequalities related to gender, class, and access to safety. A model trained on this dataset should not be interpreted as a neutral statement about who deserves survival; it is instead a summary of historical patterns. The imputation and cleaning steps were chosen to be transparent and reproducible, but they also carry assumptions. For example, age patterns differ by sex and class, so grouped imputation is more realistic than a single global median. The analysis also demonstrates that fairness and predictive accuracy are not the same thing: a model may perform well while still encoding unfair historical patterns.

## Conclusion
The results show that survival was strongly associated with sex, social class, and other structural factors rather than with a single simple rule. This supports the view that the Titanic dataset is not just a prediction problem but also a historical dataset that should be interpreted carefully and ethically.
