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
* 
![image](https://user-images.githubusercontent.com/92397144/142483668-f6f03942-02a3-4f33-8900-6a361a603d7b.png)


* Visualization 2
* Visualization 3



## Modeling
* Baseline Model (DummyRegressor)
* 
* First Simple Linear Regression (X='price_log', y='sqft_living_log')
* 
* Improved Model 1

The first multiple linear regression model that we ran has mean R-squared scores of  0.696573 and 0.717854 for the training and testing sets respectively. The mean squared errors for the training and testing sets are 41122973595.680626 and 37589240168.914894 respectively. The independent features that we used for this model are all the variables except for the 'data'. 
* 
* Improved Model 2

The second multiple linear regression model that we ran has mean R-squared scores of 0.651605 and 0.62655 for the training and testing sets respectively. The mean squared errors for the training and testing sets are 0.096902 and 0.102848 respectively.  
The independent features that we used for this model are ['bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot', 'floors',
       'waterfront', 'condition', 'grade', 'yr_built', 'sqft_living_log']. 
* 
* Improved Model 3

The third predictive model that we ran has mean R-squared scores of 0.759605 and 0.757399 for the training and testing sets respectively. The mean squared errors are lower than the last time: 0.043997 (for the training set) and 0.044998 (for the testing set). The variables 'sqft_living' and 'distance_from_bellevue' are logarithmically transformed this time to account for their original skewed distribution.
* 

* Final Model

Prior to running our final predictive model we ran a stepwise regression algorithm to pick the features that have the lowest p-values. The algorithm recommended the following features : 'distance_from_bellevue', 'view_NONE', 'floors', 'bedrooms', 'sqft_living', 'yr_built', 'sqft_lot', 'waterfront', 'sqft_basement' and 'yr_renovated'. We ran the predictive model with those returned features as our independent variables and got the following results:
Training set mean R-squared score: 0.610368, Testing set mean R-squared score: 0.620325.
The mean squared errors are 0.071229 and 0.070721 for the training and testing sets respectively. 


## Conclusions

Based on our models that we created for Windermere Real Estate which analyzes residential real estate sales in King County, Washington. The data that was used to create the model predicts price based on the features given. Based on our analysis we can safely say that houses that are closer to big cities like Seattle or Bellevue have higher prices. We can also state that Linear regression is not a good model for this data.




## Sources
* [King County Average Income](https://kingcounty.gov/independent/forecasting/King%20County%20Economic%20Indicators/Household%20Income.aspx)
* [How Long To Save For A House](https://www.cnbc.com/2018/07/13/want-to-buy-a-house-this-is-how-long-youll-have-to-save.html)
* [How Much Home Can I Afford](https://www.zillow.com/mortgage-calculator/house-affordability/)
