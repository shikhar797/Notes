AI Overview
![[svmkernel.jpeg]]

A **Support Vector Machine (SVM)** is ==a popular supervised machine learning algorithm used mainly for classification and sometimes regression tasks==. It works by finding an optimal line or boundary—called a **hyperplane**—that cleanly separates different classes of data points in a multi-dimensional space




Instead of computing coordinates in that high-dimensional space, kernels calculate the similarity (inner product) between data points, allowing SVM to form complex, non-linear decision boundaries efficient

**Handling Non-Linear Data:** If data cannot be separated by a straight line or plane in its original dimension, a kernel maps it to a higher dimension where a linear hyperplane can separate it.



```
from sklearn.svm import SVC

model = SVC(kernel='rbf')

model.fit(X_train, y_train)

y_pred = model.predict(X_test)
```




A kernel in Support Vector Machine (SVM) is ==a function that enables linear classifiers to solve non-linear problems 
by implicitly mapping input data into higher-dimensional spaces==. 

```
SVC(kernel='linear')
SVC(kernel='poly')
SVC(kernel='rbf')       # default   radical basis function
SVC(kernel='sigmoid')
```


