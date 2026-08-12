
Lazy learning and eager learning are ==two different ways machine learning algorithms handle training and prediction data==. 


## Lazy Leaner

A **lazy learner** simply stores the training data and waits until a new test query arrives before doing any real computation or classification.

- **Training speed:** Very fast because no model building or heavy math happens upfront.

- **Prediction speed:** Slow because it scans the stored data to make a decision for every single new query.

- **Memory use:** Uses high memory during testing because it keeps all training examples.

- **Example:** [K-Nearest Neighbors (KNN)](https://www.geeksforgeeks.org/machine-learning/what-is-the-difference-between-lazy-and-eager-learning/) and locally weighted




## Eager Learner


An **eager learner** builds a generalized prediction model during the training phase before receiving any test data



- **Training speed:** Slow because it spends time processing and generalizing data.

- **Prediction speed:** Fast because predictions use a pre-built model without scanning raw data.

- **Memory use:** Uses less memory during testing since the raw data can be discarded after the model is built.

- **Examples:** Decision Trees, Naive Bayes, and Support Vector Machines.