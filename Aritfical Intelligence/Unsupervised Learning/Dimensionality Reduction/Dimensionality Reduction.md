

It is a type of Unsupervised learning algorithm.

Dimensionality reduction is a technique used to reduce the number of features in a dataset while preserving important information. 
It transforms high-dimensional data into a lower-dimensional space for simpler representation.

- Reduces computation time by lowering the number of features

- Helps prevent overfitting by removing irrelevant data

- Improves data visualization and understanding


```

from sklearn.decomposition import PCA    //Principal component analysis
from sklearn.preprocessing import StandardScaler
from sklearn.datasets import load_iris

# Load dataset
data = load_iris()

X = data.data
y = data.target

# Standardize the data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Apply PCA
pca = PCA(n_components=2)

X_reduced = pca.fit_transform(X_scaled)

print("Original shape:", X.shape)
print("Reduced shape:", X_reduced.shape)
print(X_reduced)
```

