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

<img width="1029" alt="Screen Shot 2021-11-19 at 06 20 37" src="https://user-images.githubusercontent.com/92397144/142622636-8ef78e3c-3cf5-4cc4-9332-8fb21ca7c138.png">

<img width="1000" alt="Screen Shot 2021-11-19 at 06 28 08" src="https://user-images.githubusercontent.com/92397144/142623311-34b047f8-f443-4a5a-8b6d-88eb06667128.png">


<img width="1001" alt="Screen Shot 2021-11-19 at 06 24 14" src="https://user-images.githubusercontent.com/92397144/142622649-b6bb23e2-ca69-4ebc-a75e-818a567baae4.png">

                     

Simple Linear Regression <img width="396" alt="simple" src="https://user-images.githubusercontent.com/92397144/142629207-5bda44ac-6a48-4c00-a53f-27ec54d7124c.png">




<img width="1002" alt="Screen Shot 2021-11-19 at 06 41 56" src="https://user-images.githubusercontent.com/92397144/142624598-7f974cf6-c819-474c-9d2f-b60af79057e4.png">




# MOAR VISUALIZATIONS MOAR



## Modeling
We start off with a baseline model using the highest correlated variable with price, which is sqft_living. We log transform price and sqft_living to get them normally distributed.
* <b>Baseline Model (DummyRegressor)</b>
   * Baseline Train R²: 0.0
   * Baseline Test R²: -0.0007134868228084734


Our next model uses simple linear regression with the price_log and sqft_living_log variables.
* <b>Simple Linear Regression Model</b>
   * Simple LR Train R²: 0.4539365370999896
   * Simple LR Test R²: 0.45928090772142094
   * Simple LR Train RMSE: 0.3895449577221778
   * Simple LR Test RMSE: 0.3857350047602717


The following models use multiple linear regression with different features to improve our initial models.
* <b>Multiple Linear Regression Model 1</b>
   * all untouched predictor variables without normalization or scaling
   * LR1 Train R²: 0.7240453534258711
   * LR1 Test R²: 0.7253468214700272
   * LR1 Train RMSE: 193586.57723288581
   * LR1 Test RMSE: 190693.6245870106


* <b>Multiple Linear Regression Model 2</b>
   * price, sqft_living, and distance_from_bellevue outliers removed
   * LR2 Train R²: 0.8408442364433357
   * LR2 Test R²: 0.8408442364433357
   * LR2 Train RMSE: 113650.29120290976
   * LR2 Test RMSE: 196983.9676039529


* <b>Multiple Linear Regression Model 3</b>
   * maintaining model 2 with price_log, sqft_living_log, and distance_from_bellevue_log
   * LR3 Train R²: 0.8493611782756023
   * LR3 Test R²: 0.4179913127048964
   * LR3 Train RMSE: 0.18940890733449448
   * LR3 Test RMSE: 0.30383866884069294


* <b>Multiple Linear Regression Model 4</b>
   * maintaining third model with with multicollinear variables removed.
   * LR4 Train R²: 0.6595696487030089
   * LR4 Test R²: 0.5192006008921743
   * LR4 Train RMSE: 0.271438276151518
   * LR4 Test RMSE: 0.3282007564711306


* <b>Multiple Linear Regression Model 5</b>
   * maintaining fourth model with several predictor variables scaled
   * LR5 Train R²: 0.6719992640924004
   * LR5 Test R²: 0.32461768725012774
   * LR5 Train RMSE: 0.2762176976590884
   * LR5 Test RMSE: 0.3414400692863829


* <b>Multiple Linear Regression Model 6</b>
   * maintaining fifth model with only keeping selected columns provided by sklearn.feature_selection.RFE
   * LR6 Train R²: 0.5338341577464003
   * LR6 Test R²: 0.7529863316981513
   * LR6 Train RMSE: 0.3113031406383723
   * LR6 Test RMSE: 0.24701464174872836


* <b>Multiple Linear Regression Model 7</b>
   * using variables chosen by stepwise regression method
   * LR7 Train R²: 0.6134754038310046
   * LR7 Test R²: 0.526218872444935
   * LR7 Train RMSE: 0.30916120210685516
   * LR7 Test RMSE: 0.25281595772930104



## Conclusions
Based on our models that we created for Windermere Real Estate which analyzes residential real estate sales in King County, Washington. The data that was used to create the models predicts price based on the features given. From our findings we see that houses that are closer to big cities like Seattle or Bellevue have higher prices. The top two features that will positively affect prediction prices are Waterfront and Square foot living. The top two features that will negatively affect prediction price are no view and distance from Bellevue. The Linear Regression did not perform as well as we hoped. 


