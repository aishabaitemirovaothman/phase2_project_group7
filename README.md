# Linear Regression Modeling of King County Real Estate Sale Prices
<p>
<b>Authors:</b> Aisha Baitemirova-Othman, Angela Kim, Steven Addison, Wahaj Dar
<br>
<b>Instructor:</b> David Elliott
</p>


----------



![seattle](https://www.racialequityalliance.org/wp-content/uploads/2016/10/assessors_social-1.jpg)



## Overview
This project analyzes residential real estate sales in King County, Washington, and uses the data to create a model that predicts price based on the parameters given.


## Business Problem
Windermere Real Estate, based in Seattle, Washington, wants to better serve home buyers by being able to accurately present a price point using features of a house (ie. number of bedrooms) that buyers are looking for.


## Data Understanding
This dataset contains information about residential real estate sales in King County between May 2014 - May 2015. It includes details such as number of bedrooms and bathrooms, square footage of the home, and various features regarding location.


## Data Preparation & Analysis
*Correlation between predictor variables and price:*
\
![correlation heatmap](https://user-images.githubusercontent.com/79756630/142519308-558e395b-6a2e-4bbd-afa8-05cb9befe575.png)



# MOAR VISUALIZATIONS MOAR



## Modeling
We start off with a baseline model using the highest correlated variable with price, which is sqft_living. We log transform price and sqft_living to get them normally distributed.
* <b>Baseline Model (DummyRegressor)</b>
   * Baseline Train R²: 0.0
   * Baseline Test R²: -3.1441572518886574e-06


Our next model uses simple linear regression with the price_log and sqft_living_log variables.
* <b>Simple Linear Regression Model</b>
   * LR R²: 0.45511314986053364
   * LR Train Mean Squared Error: 0.1510898776130387
   * LR Test Mean Squared Error: 0.1507354170701051


The following models use multiple linear regression with different features to improve our initial models.
* <b>Multiple Linear Regression Model 1</b>
   * all untouched predictor variables without normalization or scaling
   * LR1 R²: 0.7225969246645305
   * LR1 Train Mean Squared Error: 38257931157.788956
   * LR1 Test Mean Squared Error: 34034211801.90261


* <b>Multiple Linear Regression Model 2</b>
   * price, sqft_living, and distance_from_bellevue outliers removed
   * LR2 R²: 0.7202156040231042
   * LR2 Train Mean Squared Error: 14399425171.759562
   * LR2 Test Mean Squared Error: 14579756051.437109


* <b>Multiple Linear Regression Model 3</b>
   * maintaining model 2 with price_log, sqft_living_log, and distance_from_bellevue_log
   * LR3 R²: 0.7624338571937116
   * LR3 Train Mean Squared Error: 0.043900609523814534
   * LR3 Test Mean Squared Error: 0.043306394141288895


* <b>Multiple Linear Regression Model 4</b>
   * maintaining third model with several predictor variables removed.
   * LR4 R²: 0.6202468570293977
   * LR4 Train Mean Squared Error: 0.07062364476242482
   * LR4 Test Mean Squared Error: 0.07243899357548968


* <b>Multiple Linear Regression Model 5</b>
   * maintaining fourth model with several predictor variables scaled
   * LR5 R²: 0.6113253981345041
   * LR5 Train Mean Squared Error: 0.071391459233431
   * LR5 Test Mean Squared Error: 0.07013065489395959


* <b>Multiple Linear Regression Model 6</b>
   * maintaining fifth model with only keeping selected columns provided by sklearn.feature_selection.RFE
   * LR6 R²: 0.5717866376305559
   * LR6 Train Mean Squared Error: 0.07798939005538293
   * LR6 Test Mean Squared Error: 0.08173331486415121


* <b>Multiple Linear Regression Model 7</b>
   * using variables chosen by stepwise regression method
   * LR7 R²: 0.615408636249096
   * LR7 Train Mean Squared Error: 0.07090187020262134
   * LR7 Test Mean Squared Error: 0.0716002256061957



## Conclusions
Based on our models that we created for Windermere Real Estate which analyzes residential real estate sales in King County, Washington. The data that was used to create the model predicts price based on the features given. Based on our analysis we can safely say that houses that are closer to big cities like Seattle or Bellevue have higher prices. We can also state that Linear regression is not a good model for this data.


