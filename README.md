# Stroke Data Modeling


##  Sections:   

-   Exploratory data Analysis.
-   Correlation Analysis:
    *   Continuous values correlation.(e.g. bmi and age)
    *   Categorical and continuous value correlation.(e.g Stroke and age)
    *   Categorical vs Categeorical correlation.(e.g. Stroke and heart disease)
-   Hypothesis tesing (frequentist way)- : Comparing clinical features :
    *   stroke vs no stroke.
    *   heart disease vs no heart disease.


-   Hypothesis Testing (Frequentist way): Rate of Stroke between heart disease and no heart disease.
-   Bayesian Inference (Finding Posteriors of Rate of   Stroke for heart disease vs no heart disease).
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



<img src="https://github.com/ironb25/capstone1/blob/main/images/stroke_boxplots.png" height="500" width="800">

Further, we used Central Limit theorem to plot normal distribution of population means of bmi, age and average glucose levels.


<img src="https://github.com/ironb25/capstone1/blob/main/images/stroke_lineplots.png" height="500" width="800">


### Comparing BMI, Age and Average Glucose levels with Heart disease and No heart disease using Data distribution


<img src="https://github.com/ironb25/capstone1/blob/main/images/heart_disease_boxplots.png" height="500" width="800">

#### Further, we used Central Limit theorem to plot normal distribution of population means of bmi, age and average glucose levels for Heart disease and no heart disease


<img src="https://github.com/ironb25/capstone1/blob/main/images/heart_disease_lineplots.png" height="500" width="800">

## Hypothesis Testing (Frequentist way): Rate of Stroke between heart disease and no heart disease.


-   To compare rate of stroke, we performed two sample independent t-test between males and females.

-   The difference in rate of stroke between males and females was not significant with p-value to be 0.630

## Bayesian Inference (Finding Posteriors of Rate of   Stroke for heart disease vs no heart disease)

### Bayesian Approach

-   We made the following assumptions to perform bayesian inference:
-   Rate of stroke is ~ Beta(number of stroke individuals, number of non stroke).
-   Likelihood is assumed to be binomial distribution (stroke or not).
-   Our prior can be modeled as beta and posterior is  beta conjugate prior.
-   This allows us to use beta-binomial distribution.
fitted two posterior distributions of Rate of Stroke(for heart disease individuals vs no heart disease).


<img src="https://github.com/ironb25/capstone1/blob/main/images/Bayes_heart_vs_noheart.png" height="500" width="800">


Once we have two posterior distributions, we can do hypothesis testing.With bayes hypothesis testing way, we check how probable it is that the parameter p of one site is better than the another.

#### Interpretation from above analysis after hypothesis testing : It is 100% likely that you have a higher probability of having a stroke if you have heart disease¶


## Bayesian Hypothesis Testing (Finding Posteriors of Rate of Stroke for Males and Females)

<img src="https://github.com/ironb25/capstone1/blob/main/images/Bayes_Male_vsfemale.png" height="500" width="800">

#### Interpretation : It is 74% likely that you have a higher probability of having stroke if you are a male. 

## Finding Top Risk Factors

- took positive samples for each of the individual risk factors.

- fitted a posterior distribution for each of them.



<img src="https://github.com/ironb25/capstone1/blob/main/images/Bayes_acrossfeatures.png" height="500" width="800">