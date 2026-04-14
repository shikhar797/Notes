![[Multiple Linear Regression.png]]


## Multicollinearity Problem in Multiple linear Regression
### Multicollinearity in Multiple Linear Regression

Multicollinearity arises when two or more independent variables are highly correlated with each other. This can make it difficult to find the individual contribution of each variable to the dependent variable.

****To detect multicollinearity we can use:****

1. [****Correlation Matrix****](https://www.geeksforgeeks.org/data-science/create-a-correlation-matrix-using-python/)****:**** A correlation matrix helps to find relationships between independent variables. High correlations (close to 1 or -1) suggest multicollinearity.
2. [****VIF (Variance Inflation Factor)****](https://www.geeksforgeeks.org/python/detecting-multicollinearity-with-vif-python/)****:**** VIF quantifies how much the variance of a regression coefficient increases if predictors are correlated. A high VIF typically above 10 indicates multicollinearity.