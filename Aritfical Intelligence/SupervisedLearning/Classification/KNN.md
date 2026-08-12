K‑Nearest Neighbor (KNN) is a simple and widely used machine learning technique for classification and regression tasks. 

It works by identifying the __K__ closest data points to a given input and making predictions based on the majority class or average value of those neighbors.

- Classifies data based on similarity with nearby data points
- Uses distance metrics like Euclidean distance to find nearest neighbors
- Since KNN makes no assumptions about the underlying data distribution, it makes it a non-parametric and instance-based learning method.



- ![[KNN.webp]]




```
from sklearn.neighbors import KNeighborsClassifier

knn = KNeighborsClassifier(
    n_neighbors=5,
    weights='uniform',
    metric='minkowski'
)

knn.fit(X_train, y_train)

y_pred = knn.predict(X_test)
```



```
from sklearn.neighbors import KNeighborsRegressor

knn = KNeighborsRegressor(n_neighbors=5)

knn.fit(X_train, y_train)

y_pred = knn.predict(X_test)
```

