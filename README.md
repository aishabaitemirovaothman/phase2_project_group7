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
<img width="954" alt="Screen Shot 2021-11-19 at 08 30 40" src="https://user-images.githubusercontent.com/92397144/142639411-700ab189-05e1-4dbb-ae41-dcc834d24e4b.png">

<img width="926" alt="Screen Shot 2021-11-19 at 11 26 12" src="https://user-images.githubusercontent.com/92397144/142665381-97be2775-a68b-4b6a-99e9-4b8843596672.png">

<img width="383" alt="Screen Shot 2021-11-19 at 11 18 21" src="https://user-images.githubusercontent.com/92397144/142664641-c7ebde2f-0f78-44b9-bdc9-016e47097652.png">

<img width="513" alt="Screen Shot 2021-11-19 at 11 19 26" src="https://user-images.githubusercontent.com/92397144/142664661-e4199830-2804-48df-a4e0-62b20e522857.png">

<img width="358" alt="Screen Shot 2021-11-19 at 11 20 16" src="https://user-images.githubusercontent.com/92397144/142664678-12bb4eea-952a-41d5-9e40-898f85e48c34.png">

<img width="1029" alt="Screen Shot 2021-11-19 at 06 20 37" src="https://user-images.githubusercontent.com/92397144/142622636-8ef78e3c-3cf5-4cc4-9332-8fb21ca7c138.png">

<img width="1000" alt="Screen Shot 2021-11-19 at 06 28 08" src="https://user-images.githubusercontent.com/92397144/142623311-34b047f8-f443-4a5a-8b6d-88eb06667128.png">

<img width="1001" alt="Screen Shot 2021-11-19 at 06 24 14" src="https://user-images.githubusercontent.com/92397144/142622649-b6bb23e2-ca69-4ebc-a75e-818a567baae4.png">

                     

Simple Linear Regression Plot (left) and  First Multiple Linear Regression Plot (right) 

<img width="381" alt="simple lr" src="https://user-images.githubusercontent.com/92397144/142663456-b7418c3f-7c03-4501-acc6-63b28352c969.png">. 
<img width="363" alt="lr1" src="https://user-images.githubusercontent.com/92397144/142663480-9df1f595-6250-40b4-984d-ee5dbf128fc3.png">



Second Multiple Linear Regression Plot (left) and Third Multiple Linear Regression Plot (right)

<img width="376" alt="lr2" src="https://user-images.githubusercontent.com/92397144/142663510-3586545f-dc93-44d7-a5fa-d8f0e857f5f1.png">. <img width="378" alt="lr3" src="https://user-images.githubusercontent.com/92397144/142663532-c0bef795-9da9-4efa-ac3b-4e7805650ac5.png">





Fourth Multiple Linear Regression Plot (left) and Fifth Multiple Linear Regression Plot (right)

<img width="377" alt="lr4" src="https://user-images.githubusercontent.com/92397144/142663613-291e53c4-1c0c-487a-a38b-98895a3cb0d3.png">. <img width="377" alt="lr5" src="https://user-images.githubusercontent.com/92397144/142663649-a2209f13-689e-4c67-8638-d4f5c5b9dbd0.png">




Sixth Multiple Linear Regression Plot (left) and Seventh Multiple Linear Regression Plot (right)

<img width="378" alt="lr6" src="https://user-images.githubusercontent.com/92397144/142663674-baa08fcd-b86a-4435-855b-d3982f1b510a.png">. <img width="380" alt="lr7" src="https://user-images.githubusercontent.com/92397144/142663693-4f8f9aa0-0042-4d3f-8cf5-9bcb53be7149.png">





<img width="1103" alt="Screen Shot 2021-11-19 at 11 29 42" src="https://user-images.githubusercontent.com/92397144/142665808-cf12b69b-4193-491e-9654-d90a351f9531.png">



<img width="1107" alt="Screen Shot 2021-11-19 at 11 23 50" src="https://user-images.githubusercontent.com/92397144/142665073-ca69a325-c284-410c-923a-9e3a6b0faeed.png">





## Modeling
We start off with a baseline model using the highest correlated variable with price, which is sqft_living. We log transform price and sqft_living to get them normally distributed.

<p></p>

<b>Baseline Model (DummyRegressor)</b>
 * Baseline Train R²: 0.0
 * Baseline Test R²: -7.611977848931417e-06

\
Our next model uses simple linear regression with the price_log and sqft_living_log variables.  
\
<b>Simple Linear Regression</b>  
 * Simple LR Train R²: 0.4559935622464675
 * Simple LR Test R²: 0.4533592790543598
 * Simple LR Train RMSE: 0.38932939001222455
 * Simple LR Test RMSE: 0.3863726040140355
 * Simple Condition Number: 136.8975981292544


\
The following models use multiple linear regression with different features to improve our initial models.  
\
<b>Multiple Linear Regression Model 1</b>  
  * all untouched predictor variables without normalization or scaling  
  * LR1 Train R²: 0.7227415083845596
  * LR1 Test R²: 0.7280296563595856
  * LR1 Train RMSE: 191512.90263985636
  * LR1 Test RMSE: 197177.0082445334
  * LR1 Condition Number: 1.006084430986517e+16

   

<b>Multiple Linear Regression Model 2</b>    
  * price, sqft_living, and distance_from_bellevue outliers removed.
  * LR2 Train R²: 0.7262127515210657 
  * LR2 Test R²: 0.7262127515210657
  * LR2 Train RMSE: 125672.09779613405
  * LR2 Test RMSE: 126388.69024537751
  * LR2 Condition Number: 1.0035752027694244e+16


<b>Multiple Linear Regression Model 3</b>  
  * maintaining model 2 with price_log, sqft_living_log, and distance_from_bellevue_log
  * LR3 Train R²: 0.7710735650508587
  * LR3 Test R²: 0.7664798818166713
  * LR3 Train RMSE: 0.21193655370980347
  * LR3 Test RMSE: 0.20882679492683884
  * LR3 Condition Number: 1.001320905302204e+16
  


<b>Multiple Linear Regression Model 4</b>  
  * LR4 Train R²: 0.588175511728797
  * LR4 Test R²: 0.5981068463670351
  * LR4 Train RMSE: 0.28170020490184783
  * LR4 Test RMSE: 0.2815580293362851
  * LR4 Condition Number: 9165.499808642742



<b>Multiple Linear Regression Model 5</b>  
  * maintaining fourth model with several predictor variables scaled
  * LR5 Train R²: 0.5879392642546251
  * LR5 Test R²: 0.5987762963115495
  * LR5 Train RMSE: 0.2825149340905738
  * LR5 Test RMSE: 0.27915393037643454
  * LR5 Condition Number: 24.921890162559567



<b>Multiple Linear Regression Model 6</b>  
  * maintaining fifth model with only keeping selected columns provided by sklearn.feature_selection.RFE
  * LR6 Train R²: 0.5854459587429532
  * LR6 Test R²: 0.5858729777718898
  * LR6 Train RMSE: 0.28363978204734774
  * LR6 Test RMSE: 0.28282305780280415
  * LR6 Condition Number: 24.091127817685116




<b>Multiple Linear Regression Model 7</b>  
  * using variables chosen by stepwise regression method
  * LR7 Train R²: 0.5903916264446546
  * LR7 Test R²: 0.5916737150909092
  * LR7 Train RMSE: 0.2817047366292947
  * LR7 Test RMSE: 0.281559353755675
  * LR7 Condition Number: 23.730072313671045
   


## Conclusions
After preparing the data, we made seven multiple linear regression models. Our final model was our best performing model with an R^2 value of 0.592, RMSE of 0.282, and Condition Number of 0.730. Our strongest predictor variables that will increase house prices are square footage of the house and whether the home is located on a waterfront. The strongest predictors that will decrease cost are homes with no view and being located farther from Bellevue.

Through multiple iterations of our model, we came to the conclusion that linear regression is not the best method to make a predictive model with this dataset. Linear regression is ill suited for a dataset with many categorical variables, as is the case with this dataset.

Our next steps would include gathering more data such as more recent home sales and expanding beyond single family homes into condos and apartments. We would also explore more complex modeling algorithms.
