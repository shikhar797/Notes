

Logistic Regression is a supervised machine learning algorithm used for classification problems. Unlike linear regression which predicts continuous values it predicts the probability that an input belongs to a specific class.

- It is used for binary classification where the output can be one of two possible categories such as Yes/No, True/False or 0/1.
- It uses sigmoid function to convert inputs into a probability value between 0 and 1.![[logistic_regression_vs_linear_regression.webp]]


```


from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)
```


## Assumptions of Logistic Regression

Understanding the assumptions behind logistic regression is important to ensure the model is applied correctly, main assumptions are:

1. ****Independent observations****: Each data point is assumed to be independent of the others means there should be no correlation or dependence between the input samples.
2. ****Binary dependent variables****: It takes the assumption that the dependent variable must be binary, means it can take only two values. For more than two categories [SoftMax](https://www.geeksforgeeks.org/deep-learning/what-is-softmax-classifier/) functions are used.
3. ****Linearity relationship between independent variables and log odds****: The model assumes a linear relationship between the independent variables and the log odds of the dependent variable which means the predictors affect the log odds in a linear way.
4. ****No outliers****: The dataset should not contain extreme outliers as they can distort the estimation of the logistic regression coefficients.
5. ****Large sample size****: It requires a sufficiently large sample size to produce reliable and stable results.


## ****Understanding Sigmoid Function****

1. The sigmoid function is a important part of logistic regression which is used to convert the raw output of the model into a probability value between 0 and 1.

2. This function takes any real number and maps it into the range 0 to 1 forming an "S" shaped curve called the sigmoid curve or logistic curve. Because probabilities must lie between 0 and 1, the sigmoid function is perfect for this purpose.

3. In logistic regression, we use a threshold value usually 0.5 to decide the class label.

- If the sigmoid output is same or above the threshold, the input is classified as Class 1.
- If it is below the threshold, the input is classified as Class 0.


![[Pasted image 20260213163212.png]]

