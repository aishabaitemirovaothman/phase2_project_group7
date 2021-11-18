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
* Visualization 1
* Visualization 2
* Visualization 3



## Modeling
* Baseline Model (DummyRegressor)
* 
* First Simple Linear Regression (X='price_log', y='sqft_living_log')
* 
* Improved Model 1

The first multiple linear regression model that we ran has mean R-squared scores of 0.651605 and 0.62655 for the training and testing sets respectively. The mean squared errors for the training and testing sets are 0.096902 and 0.102848 respectively.  
The independent features that we used for this model are ['bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot', 'floors',
       'waterfront', 'condition', 'grade', 'yr_built', 'sqft_living_log']. 
* 
* Improved Model 2
* 
* Improved Model 3
* 
* Improved Model 4
* 
* Final Model



## Conclusions
*
*
*



## Sources
* [King County Average Income](https://kingcounty.gov/independent/forecasting/King%20County%20Economic%20Indicators/Household%20Income.aspx)
* [How Long To Save For A House](https://www.cnbc.com/2018/07/13/want-to-buy-a-house-this-is-how-long-youll-have-to-save.html)
* [How Much Home Can I Afford](https://www.zillow.com/mortgage-calculator/house-affordability/)
