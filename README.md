# HOUSE SALE IN NORTHWESTERN COUNTY

## BUSINESS UNDERSTANDING

### INTRODUCTION
Real estate can be defined as land, natural resources and any permanent structures attached to the land including the rights to use and occupy them.Property rights give the right to ownership of land,improvement of the property and use of it.

Real estate may be classified into different categories which include ; Residential Real Estate which deals with properties used for living purpose eg apartment and houses, Commercial Real Estate ie property used for business purpose such as offices, Industrial Real Estate which are property used for industrial purpose such as processing distribution and storage, Real Estate Investment which is the use of real estate for investment purpose, Agricultural Real Estate ie property used for agricultural practices.

The value of the real estate can be influenced by number of factors which include location, size, condition, infrastructure surrounding the real estate, economic conditions, population and government policies.Real estate professionals, such as real estate agents, brokers, developers, and property managers, play crucial roles in facilitating transactions and managing properties.

### PROBLEM STATEMENT

Real estate has a number of stakeholders.These stake holders include ; buyers, sellers, real estate agents, brokers, developers, financial  institutions and lenders, tenants and the government.

All these stakeholders are interested in the value of the property and the factors most affecting the value.They need to easily and with good accuracy, predict the value of the properties they are intrested in.They also would wish to know by how much the factors are affecting the value i.e. the most crucial factors.

The method for the prediction should be easy and have a good accuracy on its prediction.This will help the stakeholders arrive on agreement more easily and quickly.It would also help the developers determine factors to consider on the development of the properties.

### OBJECTIVE

Create a method that can predict the value of real estate with a good accuracy using previous price and factors values.

# DATA UNDERSTANDING
This project uses the King County House Sales dataset.The data contain 21597 rows and 20 columns.

This data contain information on house ids, date the house were sold,built and renovated,their prices,number of rooms and bathrooms,living room and lot areas,floors,waterfronts,the views from the house, house grade,basement and house areas,zip codes,longitude and latitudes,living room and lot areas of the 15 neighbouring houses.

All this information from this data set has an impact on the overall price of the houses.Some have large effects when others have minimal impacts.We will look for the factors with large contributions to the price and use them for our contributions.

# DATA PREPARATION

replacing missing data was done on view and waterfront columns.They were replaced with none in each case.
checking for numeric column most correlated to price and correlation between them was done to find a best predictor and avoid multicollinearity .
Transforming Categorical Variables.The data had 4 important categorical variables.view,waterfront,condition and grade.


# MODELING
We will start modeling with a simple linear regression model between the area of the housing living room(sqft_living) against price.
This is because sqft_living column has the highest correlation to price compared to other numeric variables.
The first simple regression model;

price=281(sqft_living)-43989


It has R_squared of about 0.49. This means 49% of the variation in price is explained .itl has an overall p_value of 0 which is below the typical alpha of 0.05.This mean that the model is statistically significant.
The model has slope of 281 which mean an increase of sqft_living by 1 increase the price by 281 units.
the y intercept is -43989 which is means when the living area is zero the price is -43989.That does not make sense but we will transform our more advanced models for an interpretable y intercept.

#### improving the model

In our final model we use  sqft_living squared in place of sqft as it seems to improve the r_squared therefore improving our variation explanation while improving the p values.
Introduction of categorical variables in our model help improve the r_squared further explaining the variation in price.
Transforming the x axis values to be centred around the mean of sqft_living squared improves our explanation of the y intercept.

#### Regression Results
**R_squared** and **F_pvalue**
Our final regression model has R_squared of about 0.653. This means about 65% of the variation in price is explained by our model. Our model has an overall p_value of 0 which is below the typical alpha of 0.05.This means that our model is statistically significant.

**Y_intercept**
Our y_intercept is 418800 ,that is to say the price of an average size cost is about 418800 dollars on price.This is because our data is centered around the mean of sqft_living

**coeficient of sqft_living**
In the final model sqft_living is squared therefore 0.0256 is sqft_living squared hence the gradient from that will be 2(0.0256)sqft_living.which can be simply interpreted as a increase of 1% in Sqft_living will translate in about 0.0512% increase in price.

**view**
there is an increase of 164800 for view fair compared to view none,an increase of 96690 for view average compared to none,an increase of 155800 for view good as compared to none and an increase of 293100 for excellent view compared to none.

**waterfront**
There is an increase of 533600 in price for houses with waterfront compared to those that do not have a waterfront.

**condition**
we cant say anything about about condition poor and fair as they are not statistically viable.however an increase of 51490 as observed for good condition compared to average condition while an increase of 134600 is observed for houses with very good conditions compared to average

**Grade**
decrease of 122300,121300,67130 in prices is observed for houses of grade 4-low,5-fair and 6-low average respectively compared to houses of grade_7 Average. increase of 86460 ,218900, 386600, 591300, 910900 ,1764000 is seen for house of grade 8 Good,9 Better,10 Very Good, 11 Excellent, 12 Luxury, 13 Mansion respectively compared to houses of grade_7 Average.


## conclusions
1 . Statistically significant - the final model has a has an overall p_value of 0 which is below the typical alpha of 0.05.This means that our model is statistically significant.

2 . Coefficients - an increase in area (living room space which is corrirated to other areas) show a improvement of 0.0512% in price for 1% increase in area.grade,condition,view and waterfront seem to greatly improve the prices of the houses.

3 . limitation - our model provided only about 65% explanation of variation which might be small in some practical cases.

## Recommendations

1 . All the factors considered in this model should be given much considerations when dealing with house as they have proved to be statistically significant.

2 . House Grade seems to have the largest impact among catergorical data and should be given priority compared to the other categorical data.

3 . The model should be used in less variation senstive cases such as price estimation but not price setting as the r_squared is not that high.


