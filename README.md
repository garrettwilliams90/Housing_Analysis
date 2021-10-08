# Home Sales Analysis

## Project Overview

For this project, we used multiple linear regression model to predict house prices in King County, WA.

A real estate agency wants us to model the sales price of homes in King County, Washington. They will use our model to help home buyers decide whether homes are underpriced or overpriced. Due to the low inventory and high demand in housing in the King County, it is important to find good deals for home-buyers.

The price of a home can be affected by multiple predictors. We will look at which predictors are statistically significant in terms of affecting a home price. Having a real estate agency use our model will build trust between them and the home buyer. This will likely result in the homebuyer using the same real estate agency if they sell their house in the future.

## Data Overview

The Data: 
- The following link is the csv file of the original dataset:
https://github.com/garrettwilliams90/Housing_Analysis/blob/main/data/kc_house_data.csv

- The following link is the description of each column in the original dataset:
https://github.com/garrettwilliams90/Housing_Analysis/blob/main/data/column_names.md

This data gives us the house sales for homes in King County, Washington. There are 21,597 rows and 21 columns in the dataset. We will use this dataset to predict sales price for a potential home buyer. Each data entry represents a house, and includes its characteristics. Number of bedrooms, number of bathrooms, living area sq. ft., number of floors, zipcode are some of the columns in this dataset. Our target variable in this analysis is the price of the house. 

 After doing cleaning and filterings, we have 20,279 data in our final dataset!

## Methodology

We will use linear regression model for our prediction problem. We will start with baseline model, using only average house prices for our prediction, then we will use simple linear regression model by choosing the mostly correlated column with our target variable as our predictor. After doing the simple linear regression model, we will use *next_possible_feature()* function defined in the **TeamBrass.ipynb** notebook to choose our next predictors. At each iteration step, we will calculate vif score to make sure we are not having multicollinearity isuue.

We started with a baseline understanding. In the baseline model, we will only use average house prices for our prediction, and calculate the residuals accordingly. We will look R-squared values, RMSE, and MAE of both train and test sets. We knew this was going to be a poor model and the R-squared value being 0.0 proved it.

Next, for our first simple linear regression model, we only used the sq_ft_living as the predictor because it had the highest correlation to price. R-squared was 0.37 which isn't good enough. So we decided to add more predictors and make a multiple linear regression model. When we made the model, we saw that the distribution of the price was skewed. So we log transformed our target value to help improve the model.

To decide what predictors to add, we wrote a function that would iterate through all possible features and calculate the test r-squared value if the feature was added. After we picked the top feature, we checked if it was multicollinear by calculating the VIF score. If it was, we would look at adding feature that resulted in the next best r-squared value. We would then create a model with those predictors and compared it's r-squared value and RMSE with the previous model. We would also check the features p-value using the *.summary()* function to make sure coefficents of those features and the model are statistically significant.

We continued to follow this process until we got our final 5 predictors, which are 'sqft_living', 'distance', 'grade_below_average', 'waterfront' and 'view_YES' columns, and we log transformed our target value for modeling.


## Project Results

Our final model predicts 65% of the variance. 

The R-squared value is 0.65, RMSE is very close to $160,000 for both our train and test set.

The interpretation of the predictiors are as follows:
- Every 100 sqft increase in the living area, the price increases by 4 percent on average. 
- One mile increase in distance, the price decreases by 3.5 percent on average.
- If the house is on the waterfront, the price increases by 66 percent on average.
- If the house has below than the average grade, the price decreases by 18 percent on average.
- If the house has a view, the price increases by 12 percent on average.

## Conclusion

For a bargain price in King County, the house should: 

- Have less sq ft living area
- Be away from Downtown
- Not be located on waterfront
- Have no view
- Have below average grade


## Next Steps

For the next steps, we would like to redo the analysis with recent King County House Dataset, define and use more variables for the prediction, predict price per sq. ft. instead of price, and use non-linear regression model.


## Repository Navigation

### Data 

https://github.com/garrettwilliams90/Housing_Analysis/tree/main/data

### Notebooks

https://github.com/garrettwilliams90/Housing_Analysis/blob/main/TeamBrass.ipynb

https://github.com/garrettwilliams90/Housing_Analysis/blob/main/Simplified_TeamBrass.ipynb

### Presentation

https://github.com/garrettwilliams90/Housing_Analysis/blob/main/Phase%202%20Project%20presentation%20(1).pdf

### Team Members

Emine Kesici: https://github.com/emykes

Garrett Williams: https://github.com/garrettwilliams90

Derek Supino: https://github.com/djs6478














































