
Random Forest is a machine learning algorithm that uses many decision trees to make better predictions.
Each tree looks at different random parts of the data and their results are combined 
by <mark style="background: #FF5582A6;">voting for classification</mark> or <mark style="background: #FF5582A6;">averaging for regression</mark> which makes it as ensemble learning technique.

This helps in improving accuracy and reducing errors.

### Random Forest Classifier


```

from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(n_estimators=100)

model.fit(X_train, y_train)

y_pred = model.predict(X_test)
```


### Random Forest Regression

```

from sklearn.ensemble import RandomForestRegressor

model = RandomForestRegressor(
    n_estimators=100,
    random_state=42
)

model.fit(X_train, y_train)
y_pred = model.predict(X_test)
```

