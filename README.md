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

<img width="381" alt="simple" src="https://user-images.githubusercontent.com/92397144/142655247-eb224308-019d-4d1e-8d9f-22b93d462737.png">.  <img width="386" alt="lr1" src="https://user-images.githubusercontent.com/92397144/142655274-f382c491-5308-48d1-a705-2b7c4e6b3d78.png">


Second Multiple Linear Regression Plot (left) and Third Multiple Linear Regression Plot (right)

<img width="383" alt="lr2" src="https://user-images.githubusercontent.com/92397144/142655867-2a033dd3-387b-48cb-8063-e8ee6e8514ce.png">. <img width="386" alt="lr3" src="https://user-images.githubusercontent.com/92397144/142655899-84fee95f-a38c-4581-a5d1-877ff1ca0f05.png">


Fourth Multiple Linear Regression Plot (left) and Fifth Multiple Linear Regression Plot (right)

<img width="390" alt="lr4" src="https://user-images.githubusercontent.com/92397144/142656355-38a147bf-724d-4f56-a6f0-d93174aad00e.png">   <img width="384" alt="lr5" src="https://user-images.githubusercontent.com/92397144/142656420-c6fde388-0ea2-48bf-9e7c-e8dd023bb106.png">


Sixth Multiple Linear Regression Plot (left) and Seventh Multiple Linear Regression Plot (right)

<img width="389" alt="lr6" src="https://user-images.githubusercontent.com/92397144/142657021-94478b83-9abe-49ae-9892-012b3d08177a.png">  <img width="385" alt="lr7" src="https://user-images.githubusercontent.com/92397144/142657045-03a2fe17-e0a4-4019-a605-75306bebf5c8.png">




<img width="1213" alt="Screen Shot 2021-11-19 at 08 06 35" src="https://user-images.githubusercontent.com/92397144/142635753-0315880a-6d76-4d4b-95ef-e3ba22cf2774.png">




## Modeling
We start off with a baseline model using the highest correlated variable with price, which is sqft_living. We log transform price and sqft_living to get them normally distributed.
* <b>Baseline Model (DummyRegressor)</b>
  * Baseline Train R²: 0.0
  * Baseline Test R²: -7.611977848931417e-06


Our next model uses simple linear regression with the price_log and sqft_living_log variables.
    * Simple LR Train R²: 0.4559935622464675
    * Simple LR Test R²: 0.4533592790543598
    * Simple LR Train RMSE: 0.38932939001222455
    * Simple LR Test RMSE: 0.3863726040140355
    * Simple Condition Number: 136.8975981292544

  


The following models use multiple linear regression with different features to improve our initial models.
* <b>Multiple Linear Regression Model 1</b>
  * all untouched predictor variables without normalization or scaling  
  *  LR1 Train R²: 0.7227415083845596
  *  LR1 Test R²: 0.7280296563595856
  *  LR1 Train RMSE: 191512.90263985636
  *  LR1 Test RMSE: 197177.0082445334
  *  LR1 Condition Number: 1.006084430986517e+16

   


* <b>Multiple Linear Regression Model 2</b>
  * price, sqft_living, and distance_from_bellevue outliers removed.
  * LR2 Train R²: 0.7262127515210657 
  
   


* <b>Multiple Linear Regression Model 3</b>
   * maintaining model 2 with price_log, sqft_living_log, and distance_from_bellevue_log
   * 
  


* <b>Multiple Linear Regression Model 4</b>
   *


* <b>Multiple Linear Regression Model 5</b>
   * maintaining fourth model with several predictor variables scaled
   * 


* <b>Multiple Linear Regression Model 6</b>
   * maintaining fifth model with only keeping selected columns provided by sklearn.feature_selection.RFE
   * 


* <b>Multiple Linear Regression Model 7</b>
   * using variables chosen by stepwise regression method
   *
   



## Conclusions
After preparing the data, we made seven multiple linear regression models. Our final model was our best performing model with an R2 value of 0.592, RMSE of 0.282, and Condition Number of 23.73. Our strongest predictor variables that will increase house prices are square footage of the house and whether the home is located on a waterfront. The strongest predictors that will decrease cost are homes with no view and being located farther from Bellevue.

Through multiple iterations of our model, we came to the conclusion that linear regression is not the best method to make a predictive model with this dataset. Linear regression is ill suited for a dataset with many categorical variables, as is the case with this dataset.

Our next steps would include gathering more data such as more recent home sales and expanding beyond single family homes into condos and apartments. We would also explore more complex modeling algorithms.
