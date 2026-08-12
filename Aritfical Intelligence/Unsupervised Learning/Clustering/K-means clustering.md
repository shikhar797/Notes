--- 

# K-Means Clustering

### Unsupervised Learning Algorithm

K-Means groups **similar data points into clusters**
without requiring labeled data.

### Goal

> Discover natural groupings and hidden patterns in data.

---

# Why K-Means?

- Identifies **natural groupings** in unlabeled data
- Groups points based on **distance from cluster centers**
- Useful for discovering patterns in raw data
- Simple and efficient for many clustering problems

### Applications

**Customer Segmentation**  
**Image Compression**  
**Pattern Discovery**

---

# Choosing the Number of Clusters

## Elbow Method

The **Elbow Method** helps determine the optimal value of **K**.

- Run K-Means with different values of K
- Calculate the **WCSS**
- Plot K against WCSS
- Find the **elbow point**
- Select that value as K
---

![[elow method for k means clustering.png|650]]

# Example

**K = 3** is selected because the curve forms an elbow at **3**.

---

# How K-Means Works

## Step 1 — Choose K

First, decide the number of clusters.

**K = Number of clusters**

For example:

> **K = 3** → Divide the data into 3 clusters.

![[k-mean1.webp|600]]

---


## Step 2 — Initialize Centroids

K-Means initially selects **K centroids**.

Each centroid represents the center of a potential cluster.

![[k-mean2.webp|600]]

---



## Step 3 — Assign Data Points

Each data point is assigned to the **nearest centroid**.

The distance is commonly calculated using:

### Euclidean Distance

![[k-mean3.webp|600]]

---



## Step 4 — Update Centroids

The centroid of each cluster is recalculated
based on its assigned data points.

### Repeat

**Assign → Update → Assign → Update**

until the centroids stop changing significantly.

![[k-mean4.webp|600]]

---

# K-Means Algorithm

### Complete Process

**1. Choose K**

↓

**2. Initialize K centroids**

↓

**3. Assign each point to nearest centroid**

↓

**4. Recalculate centroids**

↓

**5. Repeat until convergence**

---

# K-Means — Summary

### Key Points

- **Unsupervised** learning algorithm
- Groups similar data points into **K clusters**
- Uses **distance** to assign points
- Centroids are updated iteratively
- **Elbow Method** helps choose K

### Applications

**Customer Segmentation • Image Compression • Pattern Discovery**

