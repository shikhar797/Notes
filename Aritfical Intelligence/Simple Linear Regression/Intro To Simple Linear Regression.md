
Linear regression is a type of supervised machine-learning algorithm that learns from the labelled datasets and maps the data points with most optimized linear functions which can be used for prediction on new datasets. It assumes that there is a linear relationship between the input and output, meaning the output changes at a constant rate as the input changes. This relationship is represented by a straight line.

![[introduction_to_linear_reg.webp]]


![[how_does_linear_regression_work_.webp]]



![[types_of_linear_regression.webp]]


![[challenges_in_linear_regression.webp]]


\

****For example**** we want to predict a student's exam score based on how many hours they studied. We observe that as students study more hours, their scores go up. In the example of predicting exam scores based on hours studied. Here

- ****Independent variable (input):**** Hours studied because it's the factor we control or observe.
- ****Dependent variable (output):**** Exam score because it depends on how many hours were studied.


### ***Minimizing the Error: The Least Squares Method***

To find the best-fit line, we use a method called [Least Squares](https://www.geeksforgeeks.org/maths/least-square-method/). The idea behind this method is to minimize the sum of squared differences between the actual values (data points) and the predicted values from the line. These differences are called residuals.

The formula for residuals is:
%% 
> Residual = yᵢ−y^ᵢ

**Where:***

- yᵢ is the actual observed value
- y^ᵢ is the predicted value from the line for that xᵢ

The least squares method minimizes the sum of the squared residuals:

> Σ(yᵢ−y^ᵢ)²
> 
 %%

This method ensures that the line best represents the data where the sum of the squared differences between the predicted values and actual values is as small as possible.


![[Pasted image 20260115165025.png]]'


\