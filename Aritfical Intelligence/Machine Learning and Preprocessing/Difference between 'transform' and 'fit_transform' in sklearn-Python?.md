
## The fit() Method

The fit function computes the formulation to transform the column based on [Standard scaling](https://www.geeksforgeeks.org/machine-learning/data-pre-processing-wit-sklearn-using-standard-and-minmax-scaler/) but doesn't apply the actual transformation. The computation is stored as a fit object. The fit method doesn't return anything.

## **The transform() Method**

The transform method takes advantage of the fit object in the fit() method and applies the actual transformation onto the column. So, fit() and transform() is a **two-step process** that completes the transformation in the second step. Here, Unlike the fit() method the transform method returns the actually transformed array.


Note :-
“We can directly call `transform()` on test data, provided the transformer was already fitted on the training data.  
We avoid `fit_transform()` on test data to prevent data leakage.”


## **The fit_transform() Method**

As we discussed in the above section, fit() and transform() is a two-step process, which can be brought down to a one-shot process using the fit_transform method. When the fit_transform method is used, we can compute and apply the transformation in a **single step**.
