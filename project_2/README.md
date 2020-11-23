# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Ames Housing Data and Kaggle Challenge

 - [Problem Statement](#Problem-Statement)
 - [Executive Summary](#Executive-Summary)
 - [Data Dictionary](#Data-Dictionary)
 - [Recommendations](#Recommendations)
 - [Conclusion](#Conclusion)
 - [Data Sources](#Data-Sources)

---
## Problem Statement

When it comes to buying and selling a house, homeseekers and homeowners alike are typically most concerned about one factor - that is, the price of the house. However, as houses come in all shapes and sizes, with a myriad of customizable options catering to individual preferences - such as the number of bedrooms; the size of the garage; or even the quality of the fireplace - it is difficult to perform an accurate valuation of a property. 

Nonetheless, developing a price prediction model would be immensely useful for homeseekers and homeowners to be able to estimate the sale value of their properties, allowing them to make better informed decisions. Additionally, knowing which are the specific features of a property that has a strong effect on the sale price also allows home owners to strategically up-value and market their properties.

In addition, real estate agents based in Ames may also have a vested interest in better understanding the factors affecting the current property sale prices, allowing them to identify market trends as well. 

In this project, we examine the Ames, Iowa housing dataset, which contains sale prices from 2006 to 2010 and attempt to develop a **Lasso Regession model** which predicts the price of residential properties in Ames. The model will be evaluated using the **Root Mean Squared Error (RSME)** metric which describes the average deviation of our predicted prices from the true price of the house. The lower the RMSE compared to our baseline score, the better performing the model.

---
## Executive Summary
**INTRODUCTION**

The Ames, Iowa housing dataset, comprising individual sale prices of individual residential properties from 2006 to 2010 was used for this analysis. The dataset was split into training and testing sets, with the training set containing 2051 rows and 81 features, including our target variable `SalePrice`. 

The testing set, intended for use in the Kaggle challenge submission contained 879 rows and 80 features (i.e. no `SalePrice` was present). The goal was to train and build a robust Linear Regression model to predict the `SalePrice` for each of the 879 rows in the testing set.

**METHODOLOGY**

- The training dataset was imported from the .csv file that was provided into a pandas DataFrame.
- EDA was performed to understand the various types of variables - these were differentiated accordingly (nominal, ordinal, continuous and ordinal).
- Null values were present in several features of the dataset. The significance of these null values was reviewed, and the appropriate data treatment method was established for each feature that contained null values. Outliers in the data were also identified. Data cleaning was then performed.
- Feature engineering was used to create new features that could relate to `SalePrice` in a stronger way than the individual features themselves. In addition, categorical variables were encoded to numerical features through dummy encoding.
- Data visualization was carried out in the form of histograms, scatter plots and box plots to provide useful representations of the various features in relation to `SalePrice`. Filtering was used to reduce the number of features.
- Various linear regression models: `LinearRegression`, `Lasso`, `Ridge`, `ElasticNet` were used to model the relationship between the selected features and `SalePrice`. Through iteratively removing features that had less importance in explaining the variance in our target variable, the final production model with 30 features was derived.

**KEY TAKEAWAYS AND FINDINGS**

The features with the greatest magnitude of coefficients for our finalized Lasso Regression model are as follows:

**Most positively correlated features**
- `TotalLivArea`
- `OverallQualSquared`
- `Neighborhood_StoneBr`
- `GarageArea`
- `KitchenQual`

**Most negatively correlated features**
- `MSSubClass_160`
- `MSSubClass_120`
- `Exterior1st_BrkFace`
- `MasVnrType_BrkFace`
- `HouseAge`
- `RemodYears`

The final RMSE of 25317.1156 on the test set outperforms the baseline score of 79511.73 by a fair amount.

Linear regression is one of the more simplistic supervised machine learning algorithms. However, despite the multitude of other machine learning algorithms that may offer better predictive accuracy, linear regression has its strong merits in helping us address the problem statement as well, as it provides greater interpretability of our resultant predictive features. This is due to the parameters that linear regression yields - based on the relative magnitude and direction of the coefficients, we can identify the strongest predictors in our model, as well as weigh their individual impacts on the sale price.

Coupled with our basic domain knowledge on what would influence the sale price of a house, this would also allow us to evaluate the model holistically to see if these resultant predictor features make intuitive sense or not.

---
## Data Dictionary

The data dictionary can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

---
## Recommendations 

**1. Features adding value to a home**

The total living area (including any above ground and below ground living space), as well as the overall quality and finish of the house are the most important features that increase the sale price of a house.

**2. Features lowering value to a home**

Brick masonry veneers, as well as the age of the house and the time since the last remodelling performed reduce the value of the house.

**3. Increasing value of a home**

As the size of one's house is typically already fixed, homeowners who hope to increase the value can work towards remodelling the kitchen, fireplace and basement area. Regular facade maintenance also goes a long way in bringing up the price of the house. 

**4. Neighborhoods that make good investments** 

In general, homes in Stone Brook, Northridge, Northridge Heights, Green Hills, Clear Creek, Crawford tend to be priced higher. However, it would be unwise for homeowners to use merely the location of a house to inform their investment decisions. Property prices are also influenced by many other factors such as time, property market outlook, which our model does not account for. Nonetheless, they can still use this model as a means of estimating the price of a typical house in one of these neighborhoods, keeping in mind that the dataset only contains property sale prices from years 2006 to 2010.

**5. Generalizability of model**

It is unlikely that the model will generalize well to other cities, considering some of the stronger predictors are specific to the Ames dataset (e.g. `Neighborhood`, `MSSubClass`). If we intend to make it more universal, we could attempt to throw out these predictors from the model. Additionally, if we had data of the economic indicators, interest rates, property legislative measures, there could be some basis of comparison between the two cities to try and normalize the prices accordingly.

--- 
## Conclusion

Through a data science methodology comprising exploratory data analysis, data cleaning, feature engineering, feature selection, modelling and model iteration, we have created a  **Lasso Regression model**  that is able to predict the price of a home at sale, allowing homeowners and homeseekers alike in Ames, Iowa to make informed decisions on an appropriate valuation for their homes. They are also able to better understand some of the features that would add or decrease value to a home, and carry out practicable measures to enhance the value of their houses. Real estate agents can also make use of the model to better understand the factors that influence real estate prices.

The eventual model with 30 features obtained an RMSE value of 25317.1156 on the test split of our training set.

The two most significant predictors are the  **total living area**  as well as the  **overall quality**, which both increase the overall value of the house.

Further refinements to improve our modelling process include using alternate machine learning algorithms for Recursive Feature Elimination, as well as scaling our target variable with a logarithmic transformation to reduce the effect of skew on our model. As the model currently is specific to the Ames housing dataset, it could also be improved and tweaked to be more generalizable and applicable to other cities as well.

--- 

## Data Sources
The source of the datasets used in this analysis: 
- [DSI-US-6 Project 2 Regression Challenge](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/data)
