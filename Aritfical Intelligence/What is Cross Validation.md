Cross-validation is a technique used to check how well a machine learning model performs on unseen data while preventing overfitting. It works by:

- Splitting the dataset into several parts.

- Training the model on some parts and testing it on the remaining part.

- Repeating this resampling process multiple times by choosing different parts of the dataset.

- Averaging the results from each validation step to get the final performance.


## Types of Cross-Validation

There are several types of cross-validation techniques which are as follows:

### ****1. Holdout Validation****

50 -50 :50 percent dataset for training and rest 50 percent for testing

### ****2.K-Fold Cross Validation****

[K-Fold Cross Validation](https://www.geeksforgeeks.org/r-language/k-fold-cross-validation-in-r-programming/) splits the dataset into __k__ equal-sized folds. The model is trained on __k-1__ folds and tested on the remaining fold. This process is repeated __k__ times each time using a different fold for testing.