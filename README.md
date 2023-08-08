# MGSC-310-Final-Project

WINE QUALITY PREDICTION MODEL​

MOTIVATION/BUSINESS VALUE AND VARIABLES​

- We want to determine what kinds of factors go into wine quality so that producers will be able to evaluate how to make a higher quality wine​
- Wine industry currently valued at $340 Billion​
- The industry preserves agricultural land, American jobs, attracts tourism, and generates taxes​
- Being able to make a high-quality wine can significantly increase profitability​
- We are trying to understand and predict the impact that variables have on the quality of wine​
- We are using predictors such as pH level, alcohol level, density, and citric acid levels, etc​

RAW DATA

- 12 columns (11 continuous variables and 1 categorical one)​
- 1,599 rows​
- No data cleaning required since there were no missing variables in the dataset​
- We used 70-30 Training-Test Split for our dataset on all models​
- Overall, we believed that these variables seemed to be strong indicators for predicting the quality of wine​


SUMMARY STATISTICS​

- The average wine quality can be seen to be closer to 6, with anything above it meaning good wine, while anything below the number 6 is considered bad wine

LINEAR REGRESSION(BASELINE)​​

- We use Linear Regression as our baseline model since it's easy to comprehend as well as it being computationally inexpensive​
- We find that the most statistically significant variables seem to be both alcohol content and the level of sulfate dioxide gas in the wine bottle that seem to have the biggest impact on the quality of wine at a 100% confidence level​
- The Adjusted R^2 is quite low (0.36) meaning that our predictors overall don't do a great job in explaining the variance found in the quality of wine as well not being able to predict the model as well as we thought it would​
- Not the start we wanted but we can definitely improve this model with our next two models in both accuracy and prediction in order to help wine makers improve the quality of their product to both regular customers and to wine connoisseurs​

RANDOM FOREST​

- We use an ensemble method here in order to stop the overfitting that is occurring in our model since overfitting also leads to high variance​
Both plots (minimal depth distribution and multi-way importance plot) help us determine the importance of each variable​
As seen with the linear regression model, we see that our models that are most significant are alcohol, volatile acidity, and sulphates where this can be concluded since they require the least amount of tree depth which means in a regression tree, they are seen to be at the very top of the tree​

- We use parameters such as nodesize and err.rate to reduce the variance and overfitting of our dataset along with the usual importance, ntree, and mtry parameters that are often used in bagging.​
- The importance of nodesize is fairly underestimated as it helped reduce the overfitting massively​
- Nodesize- Determines the minimum number of observations in each terminal leaf node​
- The higher the nodesize the fewer leaf nodes we have, which reduces the complexity of the model​
- When plotting the random forest function, we see that around 100 trees gave use the least amount of error with the error being constant thereafter​
- Err.rate - Slight difference, gives us a smaller difference in error size but nothing drastic​


LASSO REGRESSION​

- Similar to the linear model, variables like alcohol, sulphates, and acidity are most significant​
- Many variables have minimal significance​
- Lambda min more appropriate​
- lasso_1se coefficients have more penalization, are "shrunk" closer to zero​
- Therefore, more zero coefficients in the lasso_1se model compared to lasso_min​

PREDICTION & EVALUATION​

Choosing Lambda: ​
- Lasso_min model has smallest value of lambda, therefore lowest training error-->prone to overfitting data​
- Lasso_1se larger value of lambda, higher training error--> may be better for generalization​
​- In the context of this Lasso model, an RSME of 0.6389 means that on average, the model's predicted response values are off by approximately 0.6398 units from the actual response values.​
  Pretty good considering the values are relatively small

CONCLUSION

- we used random forest and lasso regression models compared to linear regression as our baseline  to analyze the data and concluded that alcohol, sulphates, and volatile acidity were the most important variables to predicting quality of wine​
- The use of Random Forest was due to its ease of use, flexibility for both classification and regression trees, as well as being much more accurate than bagging in the prediction of our models​
- LASSO Regression allows us to understand which variables should be considered as significant to the quality of wine and interpret it easily for management or business purposes​
- This knowledge could help producers create higher quality of wine and increase profitability for the them
