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


