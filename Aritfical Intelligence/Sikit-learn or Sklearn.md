
Sklearn requires 2D input not 1D
## 1️⃣ What is scikit-learn?

**scikit-learn** is a Python library that provides:

- Data preprocessing
    
- Supervised learning (regression & classification)
    
- Unsupervised learning (clustering, dimensionality reduction)
    
- Model evaluation & tuning
    

👉 It’s built on top of **NumPy**, **Pandas**, **SciPy**, and **Matplotlib**.

What it does **NOT** do:

- Deep learning (that’s TensorFlow / PyTorch)
    
- Big data processing (Spark is better there)


## 2️⃣ The typical Machine Learning workflow in sklearn

Almost every ML project using sklearn follows this flow:

`Load Data` 
    `↓` 
`Preprocess Data` 
     `↓`
`Split Train / Test` 
     `↓`
`Choose Model` 
    `↓` 
`Train (fit)` 
    `↓` 
`Predict` 
    `↓`
`Evaluate`


scikit-learn is designed so **every step uses the same interface**:

- `.fit()`
    
- `.transform()`
    
- `.fit_transform()`
    
- `.predict()`
    

This consistency is one of its biggest strengths.


## 3️⃣ Important sklearn modules (you WILL use these)

### 🔹 1. `sklearn.model_selection`

Used for splitting data and validation.

Common tools:

- `train_test_split`
    
- `GridSearchCV`
    
- `RandomizedSearchCV`
    
- `cross_val_score`
    

Example:

`from sklearn.model_selection import train_test_split`


### 🔹 2. `sklearn.preprocessing`

Used for **cleaning and scaling data**.

Common classes:

- `StandardScaler`
    
- `MinMaxScaler`
    
- `OneHotEncoder`
    
- `LabelEncoder`
    

Example:

`from sklearn.preprocessing import StandardScaler`

### 🔹 3. `sklearn.impute`

Used to handle **missing values**.

`from sklearn.impute import SimpleImputer`


### 🔹 4. `sklearn.linear_model`

Linear models.

Common models:

- `LinearRegression`
    
- `LogisticRegression`
    
- `Ridge`, `Lasso`


### 🔹 5. `sklearn.tree`

Tree-based models.

Common models:

- `DecisionTreeClassifier`
    
- `DecisionTreeRegressor`


### 🔹 6. `sklearn.ensemble`

Powerful ensemble models.

Common models:

- `RandomForestClassifier`
    
- `RandomForestRegressor`
    
- `GradientBoosting`
    
- `AdaBoost`


### 7. `sklearn.metrics`

Used to **evaluate model performance**.

Common functions:

- `accuracy_score`
    
- `confusion_matrix`
    
- `mean_squared_error`
    
- `classification_report`


ex->SimpleImputer

`from sklearn.impute import SimpleImputer`
`import numpy as np`

`data = [[1, 2], [3, np.nan], [7, 6]]`

`imputer = SimpleImputer(strategy="mean")`
`data_filled = imputer.fit_transform(data)`

`print(data_filled)`


### 🧩 `StandardScaler`

Scales features to mean = 0 and std = 1.

`from sklearn.preprocessing import StandardScaler`  
`scaler = StandardScaler()` 
`X_scaled = scaler.fit_transform(X)`


### 🧩 `OneHotEncoder`

Converts categorical values into numbers.

`from sklearn.preprocessing import OneHotEncoder` 
`encoder = OneHotEncoder()` 
`X_encoded = encoder.fit_transform(X_categorical)`