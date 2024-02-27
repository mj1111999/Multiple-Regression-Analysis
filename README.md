# Multiple-Regression-Analysis
Abstract—This research paper discusses about house price prediction using multiple linear regression. The dataset that was analysed on houses at King County, Seattle for year 2014-2015. The steps that were involved in analysis are dataset description, descriptive statistics, preprocessing, Model Review Selection and prediction.
Index Terms—Multiple linear regression, preprocessing, de- scriptive statistics, preprocessing, model and prediction.
I. AIM AND OBJECTIVE
The aim of this project is to use descriptive statistics and utilize multiple linear regression model to find how price of the house holds on multiple dependent variables. The reason for evaluating descriptive statistics are to find basic information of the variables in the dataset and to find connection between the variables.
A straight line is used to assess the relationship between a quantitative dependent variable and two or more independent variables in a regression model called multiple linear regres- sion.[1]
The expression for multiple linear regression is:
Y =β0 +β1 ∗b1 +β2 ∗b2 +β3 ∗b3 +...+βp ∗bp (1) The above expression is implemented using R programming.
II. DATASET DESCRIPTION AND ITS VARIABLES
The dataset provided was ”kc-house-data.csv”. This file contains 21,613 rows and 21 columns(also known as feature variables). In this dataset, it contains one single dependent variable known as price and 20 other variables as the inde- pendent variables. [2]
The description of of the given dataset is as follows:
• id - House’s identification number
• date - the day when the house was sold
• price - The price at which the house was sold
• bedrooms - How many bedrooms are there in the house.
• bathrooms - How many bathrooms are there in the house.
• sqft-living - area of living space in square feet.
• sqft-lot - Area of the lot in square feet.
• floors - How many floors are there in the house.
• waterfront - It signifies whether waterfront is present or not. If the value is ”1” then waterfront is present else it is absent.
• view - It signifies how nice the property’s view was. It ranges from 0 to 4.
• condition - It signifies the quality of the house. It ranges from 1 to 5.
• grade - Classification based on building quality, which takes into account the kind of materials and level of work- manship utilized. Better-quality (higher grade) structures cost more to construct per unit of measure and are worth more.
• sqft-above - Square feet above ground
• sqft-basement - Square feet below ground
• yr-built - Year when the house was built
• yr-renovated - Year when the house was renovated. ‘0’ if
not renovated
• zipcode - Zip code of the house
• lat - latitude of the house
• long - longitude of the house
• sqft-living15 - The mean square footage of the interior
living areas in the 15 nearest houses.
• sqft-lot15 - The mean square footage of the lots for the
15 nearest houses
III. DESCRIPTIVE STATISTICS
With R programming, there are variety of functions that can evaluate median, mean, mode, standard deviation, variance etc. Descriptive statistics is a process in which one can study and investigate the data. To identify the number of samples ’N’ nrow command was used. The min function gives the minimum value of the value of the sample, the max function gives the maximum value of the sample. Apart from the analysis of descriptive statistics, visualizations of appropriate variables were plotted as show in the figures below. [3]
IV. PREPROCESSING
In this step, the dataset analysis was done by identifying any kind duplication of records or if any kind of data which is missing before the multiple regression model was built. Also certain data types were converted into another data type of the
 Fig. 1. Descriptive Statistics
variables, for example, the waterfront variable of the housing dataset was converted to factors using as.factor() command as it was a categorical variable. A correlation plot was generated to check which variables are to be considered for multiple linear regression analysis and which variables reduces the accuracy of the analysis (as shown in Fig. 1). Certain column variables were subsetted for analysis such as date, id, sqft- above and sqft-basement. To check whether missing values are there in the dataset is.na() command was used that will return a boolean values. To identify the number of duplicated values the duplicated function was used. The price values were having values which were in billion and were expressed in ten thousands by dividing by 1000000 for ease of understanding the data. [4]
     Fig. 2. Visualizations
Fig. 3. Correlation Plot
V. MODEL ANALYSIS AND REVIEW
In order to create a linear model lm() function is used. For selecting the best model, 3 different models were analysed.
A. Model 1
For designing this model, the parameters that were consid- ered for multiple linear regression are:
1) sqft-living
2) grade
3) sqft-living15
The summary of the model was found using summary
function. The figure below is summary of model 1.
This gives the information about residuals, coefficents, F- statistic and R square values. To further understand the model, the diagnostic plots were plotted. The diagnostic plots depicts
the preliminary assumptions of multiple linear regression.

 Fig. 4. Model 1 Summary
residuals vs leverage graph .This model has influential data points.
B. Model 2
For designing this model, the parameters that were consid- ered for multiple linear regression are:
1) bedrooms 2) bathrooms 3) sqft-living 4) floors
5) waterfront 6) view
7) condition 8) grade
9) yr-built
10) yr-renovated 11) sqft-living15 12) sqft-lot15
The summary of model 2 is given in the figure below:
Fig. 6. Model 2 Summary and diagnostic plot
The diagnostic plots for model 2 is given below:
Linearity test :- for this case, the model also satisfies linearity condition
Normal distribution of errors test :- The normal Q-Q plot obtained is non-linear and positively skewed, hence normality test fails here.
No influential data points :- There is still influential data points which are in the form of outliers, hence it needs to be removed.
C. Model 3
For designing this model, the parameters that were consid- ered for multiple linear regression are:
1) bedrooms 2) bathrooms 3) floors
4) waterfront 5) view
6) condition 7) grade
8) yr-built
  Fig. 5. Model 1 Diagnostic plot
Linearity test :- The Residuals vs Fitted graphs says about linearity. There must not be any relation between residuals and fitted values and there must not be curvature in plot. This model satisfies linearity assumption.
Normal distribution of errors test :- The Normal Q-Q plot says about normal distribution of errors. A probability plot of the standardized residuals against the values that would be anticipated assuming normalcy is shown in the normal Q-Q plot. The points on this graph should lie on a straight line at an inclination of 45-degree if the normalcy assumption has been satisfied. Hence, this model does not fulfills normality assumption.
No influential data points :- The influential data points could be identified using cook’s distance. If cook’s distance is greater than 1 then it is said to have influential data points. The same can be observed in scale-location graph and

   Fig. 7. Model 2 Diagnostic plot
9) yr-renovated 10) sqft-living 11) sqft-lot
The summary of model 3 is given below:
Feature transformation was done in price variable in this case because it the plot of Q-Q plot was highly skewed. The diagnostic plot of model 3 is given above:
Linearity test :- for this case, the model satisfies the linearity condition with slight cuvature in graph.
Normal distribution of errors test :- The normal Q-Q plot obtained is linear and a 45-degree straight line was obtained. The erros are also having constant variance.
No influential data points :- There are very few influential points in the model. [5]
VI. MODEL SELECTION AND ASSUMPTIONS
A. Model Selection
Based on the 3 models generated, the model 3 was found to fulfill 3 preliminary assumptions of multiple linear regression. The r-square value of model 3 was 0.645. [6]
B. Assumptions
1) Durbin Watson Test:- It is a test to identify autocorre- lation between the variables. It ranges from 0 to 4. The durbin watson test for the best model is given below: It is evident from the results that there is no autocorrelation between the variables and with
Fig. 8. Model 3 Summary and Diagnostic Plot
Fig. 9. Durbin Watson Test Result
score of 1.96.
2) Variance Inflation Factor:- It is also a test to identify correlation between the variables. For analysis if VIF greater than 5 then there is a case of correlation. The VIF plot for the best model is given below:
3) Non-Constant Variance test:- It makes a score com- parison between the alternative, that the error variance varies with the level of the fitted values, or with a linear combination of predictors, and the hypothesis that the error variance is constant. The NCV test fails in this model. The results for NCV test are as follows:
 
   Fig. 10. Variance Inflation Factor and its plot
Fig. 11. NCV test
VII. RESULTS AND CONCLUSION
After Removing residuals and errors from the model, the fitted model is obtained. The final model also satisfies the Gauss Markov assumption. The figure below shows the fitted model:
Fig. 13. Accuracy
price = 9.860 - 0.022 * bedrooms + 0.083 * bathrooms + 0.083 * floors + 0.323 * waterfront + 0.052 * view + 0.043 * condition + 0.223 * grade - 0.005 * yr-built + 0.001 * sqft- living
REFERENCES
[1] A. Hayes, “Multiple linear regression (MLR) definition, formula, and example,” Investopedia, 08-Oct-2022. [Online]. Available: https://www.investopedia.com/terms/m/mlr.asp. [Accessed: 19-Nov- 2022].
[2] “2014-15 home sales in King County, WA,” GeoDa Data and
Lab. [Online]. Available: https://geodacenter.github.io/data-and- lab/KingCounty-HouseSales2015/. [Accessed: 19-Nov-2022].
[3] “Descriptive statistics in R,” Stats and R. [Online]. Available: https://statsandr.com/blog/descriptive-statistics-in-r/. [Accessed: 19- Nov-2022].
[4] “Data preprocessing in R,” Section. [Online]. Available: https://www.section.io/engineering-education/data-preprocessing-in-
r/. [Accessed: 19-Nov-2022].
[5] J. C. Watkins, “Organizing and Producing Data,” in An Introduction to the Science of Statistics: From Theory to Implementation, Preliminary., pp. 51–56.
[6] Clifford M. Hurvich Chih—Ling Tsai (1990) The Impact of Model Selection on Inference in Linear Regression, The American Statistician, 44:3, 214-217, DOI: 10.1080/00031305.1990.10475722
  Fig. 12. Fitted Model
The accuracy of the model was evaluated by taking absolute difference between the orignal price values and predicted price values and the difference was divided by the orignal price value. With this approach the accuracy of the model was calculated.
The equation for multiple linear regression for the house price is as follows:
