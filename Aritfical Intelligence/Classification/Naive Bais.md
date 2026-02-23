![[Pasted image 20260223100920.png]]

Naive Bayes is a machine learning classification algorithm that predicts the category of a data point using probability. **It assumes that all features are independent of each other.** Naive Bayes performs well in many real-world applications such as spam filtering, document categorisation and sentiment analysis.

#### Note:-The naive Bayes classifier assumes that all features in the input data are independent of each other, i.e. all the columns in the data are independent to each other



#### Cons of Naive Bias is :

- If categorical variable has a category (in test set), which was not observed in training data set, then model will assign a 0 (zero) probability and will be unable to make a prediction. This is often known as “Zero Frequency”. To solve this, we can use the smoothing technique. One of the simplest smoothing techniques is called Laplace estimation.


- Another limitation of this algorithm is the assumption of independent predictors. In real life, it is almost impossible that we get a set of predictors which are completely independent.
