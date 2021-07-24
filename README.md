# Stroke Data Modeling


##  Sections:   

-   Exploratory data Analysis.
-   Correlation Analysis:
    *   Continuous values correlation.(e.g. bmi and age)
    *   Categorical and continuous value correlation.(e.g Stroke and age)
    *   Categorical vs Categeorical correlation.(e.g. Stroke and heart disease)
-   Hypothesis tesing (frequentist way)- : Comparing clinical features :
    *   stroke vs no stroke,
    *    heart disease vs no heart disease,
    *   hypertension vs no hypertension.

-   Hypothesis Testing (Frequentist way): Rate of Stroke between heart disease and no heart disease.
-   Bayesian Inference (Finding Posteriors of Rate of   *  Stroke for heart disease vs no heart disease).
-   Bayesian Hypothesis Testing : Rate of Stroke if you have heart disease vs not.
-   Bayesian Hypothesis Testing : Rate of Stroke for Males vs Females.
-   Finding Top Risk factors of Stroke through Bayesian Inference.

## Background:  


-    Stroke is one of the leading causes of death in the United States.
-   This happens when blood flowing to a part of the brain stops.
-   Some of the risk factors of Stroke include age, heart disease, hypertension, diabetes.
 -  We will explore these risk factors, compare them and eventually identify top risk factors for stroke.
-   Dataset: https://www.kaggle.com/fedesoriano/stroke-prediction-dataset


## Distribution of clinical features:

### Categorical Features
![Categorical features](https://github.com/ironb25/capstone1/blob/main/images/categorical_piecharts.png)                

### Continuous Features

![Continuous features](https://github.com/ironb25/capstone1/blob/main/images/continuous_distributions.png) 


### Binary features(0 or 1)

![Binary features](https://github.com/ironb25/capstone1/blob/main/images/binary_piecharts.png) 

## Correlation Analysis

### Correlation between continuous value features

- Comparison of clinical features Age,BMI and Avg glucose levels

![Correlation](https://github.com/ironb25/capstone1/blob/main/images/correlationfig.png) 

### categorical vs continuous correlation

-   Like all correlation analyses the Point-Biserial Correlation measures the strength of association or co-occurrence between two variables. (categorical vs continuous)
- e.g.  indicates a positive relationship between the math score and passing the final exam or failing it. 
- We correlated stroke and heart disease which are categorical features to age.

    ```
    stats.pointbiserialr(df['stroke'].astype(int), df['age'])
    ``` 
    ```
    stats.pointbiserialr(df['heart_disease'].astype(int), df['age']) ```
- We got statistically significant p-value <.0001 for both cases implying both stroke and heart disease have strong association.

## Hypothesis Testing

### Comparing BMI, Age and Average Glucose levels with Stroke and No Stroke using Data distribution

![StrokeBoxplots](https://github.com/ironb25/capstone1/blob/main/images/stroke_boxplots.png) 

Further, we used Central Limit theorem to plot normal distribution of population means of bmi, age and average glucose levels.

![StrokeLineplots](https://github.com/ironb25/capstone1/blob/main/images/stroke_lineplots.png) 

### Comparing BMI, Age and Average Glucose levels with Heart disease and No heart disease using Data distribution

![heartBoxplots](https://github.com/ironb25/capstone1/blob/main/images/heart_disease_boxplots.png) 

Further, we used Central Limit theorem to plot normal distribution of population means of bmi, age and average glucose levels for Heart disease and no heart disease

![heartLineplots](https://github.com/ironb25/capstone1/blob/main/images/heart_disease_lineplots.png) 