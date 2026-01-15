## What is Feature Scaling?

**Feature scaling** is the process of **bringing all numerical features to a similar scale (range)** so that no feature dominates others just because of its size.

In simple words:

> **Feature scaling makes numbers comparable.**

---

## Why is feature scaling needed?

Real datasets contain features with **very different ranges**.

### Example (before scaling):

|Feature|Values|
|---|---|
|Age|18 – 60|
|Salary|20,000 – 2,000,000|

Here:

- Salary values are **huge**
    
- Age values are **small**
    

A machine learning model may think:

> Salary is more important just because the numbers are bigger

This is **wrong**.

Feature scaling fixes this problem.

---

## What problem happens without scaling?

Many ML models:

- Use **distance**
    
- Use **gradients**
    
- Use **mathematical optimization**
    

Large values:

- Dominate calculations
    
- Slow down learning
    
- Give biased results
    

So:

> Bigger numbers ≠ More important features

---

## What does feature scaling do?

Feature scaling:

- Shrinks large values
    
- Expands small values
    
- Keeps the **relative meaning** of the data
    

After scaling:

- All features live in a **similar range**
    
- Models learn **faster and better**
    

---

## Common types of feature scaling

### 1️⃣ Standardization (Standard Scaling)

This method:

- Centers data around **0**
    
- Makes the spread roughly **1**
    

Conceptually:

`Most values end up between -3 and +3`

Used when:

- Data follows a normal distribution
    
- Models use gradients or distances
    ![[Pasted image 20260115142239.png]]


Examples:

- Logistic Regression
    
- Linear Regression
    
- SVM
    
- KNN
    
- PCA
    

---

### 2️⃣ Normalization (Min-Max Scaling)

This method:

- Converts data into a **fixed range**
    
- Usually between **0 and 1**
    

Conceptually:

`Smallest value → 0 Largest value → 1`

Used when:

- You want bounded values
    
- You want to preserve shape of data
    
![[Pasted image 20260115142324.png]]


Examples:

- Neural networks
    
- KNN
    
- Image processing
    

---

## Which models NEED feature scaling?

### ✅ Scaling is IMPORTANT for:

- Linear Regression
    
- Logistic Regression
    
- Support Vector Machines (SVM)
    
- K-Nearest Neighbors (KNN)
    
- PCA
    
- Gradient Descent–based models
    

Because these models:

- Use distance
    
- Use dot products
    
- Use optimization
    

---

### ❌ Scaling is NOT required for:

- Decision Trees
    
- Random Forest
    
- Gradient Boosting
    
- XGBoost
    

Why?

- They split data using **rules**, not distances
    

---