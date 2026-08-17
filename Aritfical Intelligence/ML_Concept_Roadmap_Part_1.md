---
marp: true
theme: black
paginate: true
---

# ML Concept Roadmap

## Understanding Major Terminology of Machine Learning

### Part 1 — Fundamentals, Data, Preprocessing & Training

---

# 1. Artificial Intelligence

### Definition
**Artificial Intelligence (AI)** is the field of computer science focused on creating systems that can perform tasks that normally require human intelligence.

### Example
- Speech recognition
- Image recognition
- Chatbots
- Autonomous driving

### Key Idea
> AI is the **broadest field** that includes Machine Learning and Deep Learning.

---

# 2. Machine Learning

### Definition
**Machine Learning (ML)** is a subset of AI where systems learn patterns from data to make predictions or decisions without being explicitly programmed for every rule.

### Example

Instead of programming:

```text
IF email contains "win money"
→ Spam
```

We give the model many examples of spam and non-spam emails.

### Key Idea
> **Data → Learning → Prediction**

---

# 3. Deep Learning

### Definition
**Deep Learning** is a subset of Machine Learning that uses neural networks with multiple layers to learn complex patterns from data.

### Example

```text
Pixels → Edges → Shapes → Objects
```

A CNN can use these learned representations to identify whether an image contains a cat or dog.

### Key Idea
> Deep Learning uses **multi-layer neural networks** to automatically learn representations.

---

# 4. Data Science

### Definition
**Data Science** combines statistics, programming, mathematics and domain knowledge to extract useful insights and knowledge from data.

### Example

A company analyzes customer data to determine:

- Who is likely to leave?
- Which product sells most?
- Which customers should receive an offer?

### Key Idea
> Data Science focuses on **extracting value from data**.

---

# 5. Supervised Learning

### Definition
**Supervised Learning** learns a mapping between inputs and known outputs using labeled data.

### Example

```text
Input                  Label
--------------------------------
House features   →     Price
Email            →     Spam / Not Spam
```

### Common Tasks
- Classification
- Regression

### Key Idea
> The model learns from **input-output pairs**.

---

# 6. Unsupervised Learning

### Definition
**Unsupervised Learning** finds patterns or structures in data without predefined labels.

### Example

A company groups customers based on:

```text
Age
Income
Spending
```

without telling the algorithm which customer belongs to which group.

### Common Tasks
- Clustering
- Dimensionality Reduction

### Key Idea
> **No target labels are provided.**

---

# 7. Semi-Supervised Learning

### Definition
**Semi-Supervised Learning** uses a small amount of labeled data together with a large amount of unlabeled data.

### Example

```text
100 labeled images
+
10,000 unlabeled images
```

The model uses both to improve learning.

### Why?
Labeling large datasets can be expensive and time-consuming.

### Key Idea
> **Small labeled dataset + large unlabeled dataset**

---

# 8. Reinforcement Learning

### Definition
**Reinforcement Learning (RL)** is a learning approach where an agent learns by interacting with an environment and receiving rewards or penalties.

### Example

```text
Action → Environment → Reward
```

Winning → Positive reward  
Losing → Negative reward

### Key Idea
> The agent learns **which actions maximize long-term reward**.

---

# 9. Classification

### Definition
**Classification** is a supervised learning task where the model predicts a discrete category or class.

### Example

```text
Email → Spam
Email → Not Spam
```

### Types
- Binary classification
- Multiclass classification
- Multilabel classification

### Key Idea
> Output is a **category**.

---

# 10. Regression

### Definition
**Regression** is a supervised learning task where the model predicts a continuous numerical value.

### Example

```text
House Features
      ↓
ML Model
      ↓
₹65,00,000
```

### Common Applications
- House-price prediction
- Sales forecasting
- Temperature prediction

### Key Idea
> Output is a **continuous numerical value**.

---

# Category 2
# Data & Dataset Concepts

---

# 11. Dataset

### Definition
A **dataset** is a collection of data used for analysis or machine learning.

### Example

| Area | Bedrooms | Location | Price |
|---|---:|---|---:|
| 1200 | 2 | Delhi | ₹50L |
| 1800 | 3 | Noida | ₹75L |

### Key Idea
> A dataset contains the **examples used by the ML system**.

---

# 12. Training Set

### Definition
The **training set** is the portion of data used to train the machine-learning model.

### Example

```text
Dataset
   ↓
70% → Training
```

The model learns patterns from this data.

### Key Idea
> Training data is used to **learn model parameters**.

---

# 13. Validation Set

### Definition
The **validation set** is used during model development to select models and tune hyperparameters.

### Example

```text
Dataset
 ├── 70% Training
 ├── 15% Validation
 └── 15% Test
```

### Key Idea
> Validation data helps us **choose and tune the model**.

---

# 14. Test Set

### Definition
The **test set** is unseen data used to evaluate the final model's generalization performance.

### Example

```text
Training → Learn
Validation → Tune
Test → Final Evaluation
```

### Key Idea
> The test set should be used **only for final evaluation**.

---

# 15. Features

### Definition
**Features** are input variables used by a machine-learning model to make predictions.

### Example

For house-price prediction:

```text
Area
Bedrooms
Location
Age
```

are features.

### Notation

```text
X = Features
y = Target
```

### Key Idea
> Features are the **information given to the model**.

---

# 16. Labels

### Definition
A **label** is the known output associated with a training example in supervised learning.

### Example

```text
Features              Label
--------------------------------
Email content    →    Spam
House features   →    ₹60L
```

### Key Idea
> A label tells the model **what the correct answer is** during training.

---

# 17. Instances

### Definition
An **instance** is a single observation or example in a dataset.

### Example

```text
Dataset:
1000 customer records

→ Each customer record = 1 instance
```

### Key Idea
> Instance = **one data point / one observation**.

---

# 18. Target Variable

### Definition
The **target variable** is the variable that a supervised learning model attempts to predict.

### Example

```text
Area + Bedrooms + Location
            ↓
          Price
```

Here:

```text
Price = Target
```

### Key Idea
> Target = **what the model is trying to predict**.

---

# 19. Structured Data

### Definition
**Structured data** is data organized in a predefined format, usually rows and columns.

### Example

| Age | Salary | City |
|---:|---:|---|
| 22 | 40000 | Delhi |
| 25 | 55000 | Noida |

### Common Sources
- SQL databases
- Spreadsheets
- CSV files

### Key Idea
> Structured data has a **well-defined schema**.

---

# 20. Unstructured Data

### Definition
**Unstructured data** does not follow a fixed tabular structure.

### Examples
- Images
- Videos
- Audio
- Text
- Social-media posts

### Example

```text
"Today's market is looking very bullish!"
```

### Key Idea
> Unstructured data often requires specialized preprocessing.

---

# Category 3
# Data Preprocessing

---

# 21. Missing Values

### Definition
**Missing values** occur when some observations do not contain a value for a feature.

### Example

| Age | Salary |
|---:|---:|
| 25 | 40000 |
| 30 | NULL |
| 28 | 50000 |

### Common Solutions
- Remove rows
- Mean/median imputation
- Mode imputation
- Model-based imputation

### Key Idea
> Missing data must be handled before many ML algorithms can use it.

---

# 22. Duplicate Data

### Definition
**Duplicate data** occurs when the same observation appears more than once.

### Example

```text
ID   Name
1    Rahul
2    Amit
1    Rahul  ← Duplicate
```

### Problem
Duplicates can distort:

- Statistics
- Model training
- Class distributions

### Key Idea
> Identify and remove **unnecessary duplicate observations**.

---

# 23. Outliers

### Definition
An **outlier** is an observation that is unusually far from the rest of the data.

### Example

```text
Salary:
30k
32k
35k
34k
5,00,000  ← Outlier
```

### Detection Methods
- IQR
- Z-score
- Visualization

### Key Idea
> Outliers can represent **errors or genuine rare events**.

---

# 24. Noise

### Definition
**Noise** is random or irrelevant variation in data that does not represent the underlying pattern.

### Example

A temperature sensor normally records:

```text
25°C
25.2°C
25.1°C
25.3°C
```

A sudden:

```text
85°C
```

may be sensor noise.

### Key Idea
> Noise makes it harder for a model to learn the **true pattern**.

---

# 25. Feature Scaling

### Definition
**Feature scaling** transforms numerical features so that their values are on comparable scales.

### Example

```text
Age:      18–60
Salary:   20,000–2,00,000
```

Salary dominates numerically.

Scaling makes the ranges more comparable.

### Important For
- KNN
- SVM
- K-Means
- Gradient-based models

### Key Idea
> Scaling prevents large-valued features from dominating distance or optimization calculations.

---

# 26. Standardization

### Definition
**Standardization** transforms data so that it approximately has:

```text
Mean = 0
Standard Deviation = 1
```

### Formula

\[
$$
z = \frac{x-\mu}{\sigma}
$$
\]

### Example

If:

```text
x = 70
μ = 50
σ = 10
```

then:

```text
z = 2
```

### Key Idea
> Standardization converts values into **z-scores**.

---

# 27. Normalization

### Definition
**Normalization** commonly scales values to a fixed range, often **0 to 1**.

### Min-Max Formula

\[
$$
x' = \frac{x-x_{min}}
{x_{max}-x_{min}}
$$
\]

### Example

If:

```text
x = 50
min = 0
max = 100
```

then:

```text
x' = 0.5
```

### Key Idea
> Normalization maps values to a **bounded range**.

---

# 28. One-Hot Encoding

### Definition
**One-Hot Encoding** converts categorical values into separate binary columns.

### Example

Original:

```text
Color
-----
Red
Blue
Green
```

After encoding:

| Red | Blue | Green |
|---:|---:|---:|
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 0 | 0 | 1 |

### Key Idea
> Each category gets its **own binary feature**.

---

# 29. Label Encoding

### Definition
**Label Encoding** converts categories into numerical values.

### Example

```text
Low    → 0
Medium → 1
High   → 2
```

### Advantage
Simple and memory efficient.

### Important
For nominal categories, arbitrary numeric values can incorrectly imply an ordering.

### Key Idea
> Categories are represented using **integer codes**.

---

# 30. Data Cleaning

### Definition
**Data Cleaning** is the process of detecting and correcting inaccurate, incomplete, inconsistent, duplicate or irrelevant data.

### Common Tasks

```text
Missing values
Duplicates
Invalid values
Inconsistent formats
Outliers
Noise
```

### Example

```text
"Delhi"
"delhi"
"DELHI"
```

can be standardized to:

```text
"Delhi"
```

### Key Idea
> Clean data improves the **quality and reliability** of ML models.

---

# Category 4
# Feature Engineering

---

# 31. Feature Engineering

### Definition
**Feature Engineering** is the process of creating, transforming or selecting features to improve machine-learning performance.

### Example

From:

```text
Date of Birth
```

create:

```text
Age
```

### Another Example

```text
Height + Weight
       ↓
      BMI
```

### Key Idea
> Transform raw data into **useful model inputs**.

---

# 32. Feature Selection

### Definition
**Feature Selection** is the process of selecting the most useful features while removing irrelevant or redundant ones.

### Example

Suppose we have:

```text
Age
Salary
City
Customer ID
Random Number
```

A model may not need:

```text
Customer ID
Random Number
```

### Benefits
- Reduces dimensionality
- Faster training
- Less overfitting
- Better interpretability

### Key Idea
> Keep useful features and **remove unnecessary ones**.

---

# 33. Feature Extraction

### Definition
**Feature Extraction** transforms existing raw data into a new, smaller or more informative representation.

### Example

An image may contain:

```text
Millions of pixels
        ↓
Extract useful visual features
```

### NLP Example

```text
Text
 ↓
TF-IDF vectors
```

### Key Idea
> Convert raw data into a **useful feature representation**.

---

# 34. PCA

### Definition
**Principal Component Analysis (PCA)** is a dimensionality-reduction technique that transforms correlated features into a smaller set of uncorrelated principal components.

### Example

```text
100 Features
      ↓
     PCA
      ↓
10 Principal Components
```

### Main Goal
Preserve as much variance as possible using fewer dimensions.

### Key Idea
> PCA finds directions that capture **maximum variance**.

---

# 35. Correlation

### Definition
**Correlation** measures the strength and direction of the relationship between two variables.

### Range

```text
-1 ≤ r ≤ +1
```

### Interpretation

```text
+1 → Strong positive relationship
 0 → No linear relationship
-1 → Strong negative relationship
```

### Example

```text
Study Time ↑
      ↓
Exam Score ↑
```

may indicate positive correlation.

### Key Idea
> Correlation measures **association**, not necessarily causation.

---

# 36. Multicollinearity

### Definition
**Multicollinearity** occurs when two or more independent features are highly correlated with each other.

### Example

```text
Age in years
Age in months
```

contain almost the same information.

### Problem
It can make coefficient estimates unstable in linear models.

### Detection
- Correlation matrix
- VIF

### Key Idea
> Multiple features provide **similar information**.

---

# 37. Curse of Dimensionality

### Definition
The **Curse of Dimensionality** describes problems that occur when the number of features becomes very large.

### Problems
- Data becomes sparse
- Distance measures become less meaningful
- More computation
- Higher risk of overfitting

### Example

```text
5 features → manageable
5000 features → potentially problematic
```

### Key Idea
> High-dimensional spaces require **more data and careful feature management**.

---

# 38. Dimensionality Reduction

### Definition
**Dimensionality Reduction** reduces the number of features while attempting to preserve important information.

### Example

```text
100 features
      ↓
Dimensionality Reduction
      ↓
10 features
```

### Techniques
- PCA
- LDA
- Autoencoders

### Key Idea
> Fewer dimensions can mean **less complexity and faster learning**.

---

# 39. Feature Importance

### Definition
**Feature Importance** measures how useful each feature is for making predictions.

### Example

For house-price prediction:

```text
Area       → 0.45
Location   → 0.30
Bedrooms   → 0.15
Age        → 0.10
```

### Common Methods
- Tree-based importance
- Permutation importance

### Key Idea
> It helps answer: **Which features matter most to the model?**

---

# 40. SHAP Values

### Definition
**SHAP (SHapley Additive exPlanations)** values explain how individual features contribute to a model's prediction.

### Example

For a house prediction:

```text
Base prediction = ₹50L

Large area      → +₹10L
Good location   → +₹8L
Old building    → -₹3L

Final prediction = ₹65L
```

### Key Idea
> SHAP explains **how each feature pushes a prediction higher or lower**.

---

# Category 5
# Model Training

---

# 41. Training

### Definition
**Training** is the process of learning model parameters from training data.

### Example

```text
Training Data
     ↓
Model
     ↓
Learn Parameters
```

### Example
Linear regression learns:

```text
w₁, w₂, ..., b
```

### Key Idea
> Training is where the model **learns from data**.

---

# 42. Testing

### Definition
**Testing** is the process of evaluating a trained model on previously unseen test data.

### Example

```text
Train → Learn
Test  → Evaluate
```

### Key Idea
> Testing measures how well the model **generalizes to unseen data**.

---

# 43. Validation

### Definition
**Validation** evaluates model performance during development and helps select hyperparameters or models.

### Example

```text
Model A → Validation Score
Model B → Validation Score
Model C → Validation Score
```

Choose the model based on validation performance.

### Key Idea
> Validation helps make **development decisions** before final testing.

---

# 44. Epoch

### Definition
An **epoch** is one complete pass through the entire training dataset during iterative model training.

### Example

If there are:

```text
10,000 training examples
```

and the model processes all 10,000 once:

```text
1 epoch
```

### Example

```text
Epoch 1 → Dataset once
Epoch 2 → Dataset again
Epoch 3 → Dataset again
```

### Key Idea
> One epoch = **one complete pass through training data**.

---

# 45. Batch

### Definition
A **batch** is a subset of training examples processed together before updating model parameters.

### Example

```text
Dataset = 10,000 examples
Batch size = 100
```

The model processes:

```text
100 examples → update
100 examples → update
...
```

### Key Idea
> Batch size determines **how many examples are processed per update**.

---

# 46. Iteration

### Definition
An **iteration** is one model update based on one batch of training data.

### Example

```text
10,000 examples
Batch size = 100

Iterations per epoch = 100
```

### Formula

\[
$$
Iterations \approx \frac{Dataset\ Size}{Batch\ Size}
$$
\]

### Key Idea
> **One batch → one parameter update → one iteration.**

---

# 47. Learning Rate

### Definition
The **learning rate** controls how much model parameters are changed during each optimization step.

### Example

```text
Small learning rate
→ Slow but controlled learning

Large learning rate
→ Faster but may overshoot
```

### Key Idea
> Learning rate controls the **step size during optimization**.

---

# 48. Optimizer

### Definition
An **optimizer** is an algorithm that updates model parameters to minimize the loss function.

### Examples
- Gradient Descent
- SGD
- Adam
- RMSProp

### Process

```text
Loss
 ↓
Gradient
 ↓
Optimizer
 ↓
Update Parameters
```

### Key Idea
> Optimizer determines **how the model learns its parameters**.

---

# 49. Cost Function

### Definition
A **cost function** measures the overall error of a model across the training dataset.

### Example

For regression, Mean Squared Error can be used:

\[
$$
MSE = \frac{1}{n}\sum(y-\hat y)^2
$$
\]

### Goal

```text
Minimize Cost
```

### Key Idea
> Cost represents the **overall objective/error across examples**.

---

# 50. Loss Function

### Definition
A **loss function** measures the error between a model's prediction and the actual value, typically for an individual training example.

### Example

Actual:

```text
100
```

Prediction:

```text
90
```

The loss quantifies the prediction error.

### Examples
- MSE
- MAE
- Cross-Entropy
- Hinge Loss

### Cost vs Loss

```text
Loss → Error for individual examples
Cost → Aggregate objective over dataset
```

### Key Idea
> The model tries to **minimize the loss/cost objective** during training.

---

# Part 1 Complete

## Concepts Covered

```text
1–10    → ML Fundamentals
11–20   → Data & Dataset Concepts
21–30   → Data Preprocessing
31–40   → Feature Engineering
41–50   → Model Training
```

## Next Part

### Model Performance & Optimization

```text
51. Accuracy
52. Precision
53. Recall
54. Specificity
55. Sensitivity
56. F1 Score
57. ROC Curve
58. ROC-AUC
59. PR Curve
60. PR-AUC

61–70 → Regression Metrics
71–80 → Model Problems
81–90 → Optimization
```
