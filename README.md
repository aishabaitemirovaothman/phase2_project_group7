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
![correlation heatmap]<img width="954" alt="Screen Shot 2021-11-19 at 08 30 40" src="https://user-images.githubusercontent.com/92397144/142639411-700ab189-05e1-4dbb-ae41-dcc834d24e4b.png">


<img width="1029" alt="Screen Shot 2021-11-19 at 06 20 37" src="https://user-images.githubusercontent.com/92397144/142622636-8ef78e3c-3cf5-4cc4-9332-8fb21ca7c138.png">

<img width="1000" alt="Screen Shot 2021-11-19 at 06 28 08" src="https://user-images.githubusercontent.com/92397144/142623311-34b047f8-f443-4a5a-8b6d-88eb06667128.png">


<img width="1001" alt="Screen Shot 2021-11-19 at 06 24 14" src="https://user-images.githubusercontent.com/92397144/142622649-b6bb23e2-ca69-4ebc-a75e-818a567baae4.png">

                     

Simple Linear Regression Plot (left)                                    and  First Multiple Linear Regression Plot (right) 

<img width="396" alt="simple" src="https://user-images.githubusercontent.com/92397144/142629207-5bda44ac-6a48-4c00-a53f-27ec54d7124c.png">.  <img width="376" alt="lr1" src="https://user-images.githubusercontent.com/92397144/142629346-dcaa57e1-ba4c-4a12-b2a9-5bf82abfe1dc.png">


Second Multiple Linear Regression Plot (left) and Third Multiple Linear Regression Plot (right)

<img width="383" alt="lr2" src="https://user-images.githubusercontent.com/92397144/142631469-a34dc09e-39b1-460f-97d2-68eb4c037cff.png">.  <img width="393" alt="lr3" src="https://user-images.githubusercontent.com/92397144/142631490-7c1bd2b5-c5a5-43ee-ab4b-93a5f982bcb0.png">


Fourth Multiple Linear Regression Plot (left) and Fifth Multiple Linear Regression Plot (right)

<img width="394" alt="lr4" src="https://user-images.githubusercontent.com/92397144/142632655-62b1b086-6cb0-40ca-973a-84b8929df112.png">. <img width="390" alt="lr5" src="https://user-images.githubusercontent.com/92397144/142632671-db219347-d75f-4cae-9e30-57af6fc10a2c.png">


Sixth Multiple Linear Regression Plot (left) and Seventh Multiple Linear Regression Plot (right)

<img width="391" alt="lr6" src="https://user-images.githubusercontent.com/92397144/142632803-11a6f96a-9e13-4fed-953c-439a94a596fe.png">. <img width="383" alt="lr7" src="https://user-images.githubusercontent.com/92397144/142633135-b2895481-2244-4778-9927-50cd5ebe5ec8.png">


<img width="1213" alt="Screen Shot 2021-11-19 at 08 06 35" src="https://user-images.githubusercontent.com/92397144/142635753-0315880a-6d76-4d4b-95ef-e3ba22cf2774.png">




## Modeling
We start off with a baseline model using the highest correlated variable with price, which is sqft_living. We log transform price and sqft_living to get them normally distributed.
* <b>Baseline Model (DummyRegressor)</b>
   * Baseline Train R²: 0.0
   * Baseline Test R²: -0.0005141387181422097


Our next model uses simple linear regression with the price_log and sqft_living_log variables.
* <b>Simple Linear Regression Model</b>
* Simple LR Train R²: 0.4565445446385986
* Simple LR Test R²: 0.4515873022050134
* Simple LR Train RMSE: 0.38809026782193695
* Simple LR Test RMSE: 0.3900781771542754

  


The following models use multiple linear regression with different features to improve our initial models.
* <b>Multiple Linear Regression Model 1</b>
   * all untouched predictor variables without normalization or scaling
   * LR1 Train R²: 0.7240530302153445
   * LR1 Test R²: 0.7252312774532106
   * LR1 Train RMSE: 195222.9705641599
   * LR1 Test RMSE: 185656.5523896629

   


* <b>Multiple Linear Regression Model 2</b>
   * price, sqft_living, and distance_from_bellevue outliers removed
   * LR2 Train R²: 0.7229942448345197
   * LR2 Test R²: 0.7229942448345197
   * LR2 Train RMSE: 125261.54344907528
   * LR2 Test RMSE: 127492.48257594123
   


* <b>Multiple Linear Regression Model 3</b>
   * maintaining model 2 with price_log, sqft_living_log, and distance_from_bellevue_log
   * LR3 Train R²: 0.7705456474009538
   * LR3 Test R²: 0.767801957776184
   * LR3 Train RMSE: 0.21087371204652933
   * LR3 Test RMSE: 0.21210114989758455
  


* <b>Multiple Linear Regression Model 4</b>
   * maintaining third model with with multicollinear variables removed.
   * LR4 Train R²: 0.5918253584624475
   * LR4 Test R²: 0.5869214550514928
   * LR4 Train RMSE: 0.2823128860273679
   * LR4 Test RMSE: 0.2798283992518389


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


