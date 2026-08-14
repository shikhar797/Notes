---
theme: night
transition: slide
slideNumber: true
---

# Machine Learning & AI Interview Prep
## Deep-Dive Obsidian Slide Deck with Definitions & Examples

---

## Category 6: Model Performance

---

### 51. Accuracy
- **Definition:** The proportion of correctly predicted instances (both true positives and true negatives) out of the total number of evaluated samples.
- **Formula:** $\frac{TP + TN}{TP + TN + FP + FN}$
- **Real-World Example:** In a balanced dataset predicting whether a customer will renew a subscription (50% yes, 50% no), an accuracy of 92% means 92 out of 100 predictions were correct.
- **Interview Note:** Never rely on accuracy for imbalanced datasets! In fraud detection with 99% non-fraud cases, a model predicting "non-fraud" every time achieves 99% accuracy while being useless.

---

### 52. Precision
- **Definition:** The proportion of predicted positive cases that were actually positive. It measures the reliability of positive predictions.
- **Formula:** $\frac{TP}{TP + FP}$
- **Real-World Example:** In an email spam filter, Precision measures: *"Of all emails flagged as spam, how many were actually spam?"*
- **When it Matters:** High precision is critical when **False Positives are costly** (e.g., locking a legitimate account on suspicious activity).

---

### 53. Recall (Sensitivity)
- **Definition:** The proportion of actual positive cases that were correctly identified by the model. It measures coverage.
- **Formula:** $rac{TP}{TP + FN}$
- **Real-World Example:** In cancer diagnosis, Recall measures: *"Of all patients who actually have cancer, how many did the test catch?"*
- **When it Matters:** High recall is critical when **False Negatives are dangerous or fatal**.

---

### 54. Specificity
- **Definition:** The proportion of actual negative cases correctly identified as negative (True Negative Rate).
- **Formula:** $\frac{TN}{TN + FP}$
- **Real-World Example:** In drug testing, Specificity measures the model's ability to correctly clear individuals who are not taking prohibited substances.
- **Interview Note:** Specificity is the negative counterpart to Sensitivity (Recall). Used widely in medical diagnostics.

---

### 55. Sensitivity
- **Definition:** Mathematically identical to **Recall** (True Positive Rate). It measures the probability of a positive test result given that the condition is present.
- **Formula:** $\frac{TP}{TP + FN}$
- **Real-World Example:** In COVID-19 rapid antigen testing, sensitivity indicates how effectively the test flags infected individuals.

---

### 75. Bias-Variance Trade-off
- **Definition:** The fundamental machine learning trade-off where **Bias** (error from overly simple assumptions) and **Variance** (error from extreme sensitivity to training data fluctuations) must be balanced to minimize total generalization error.
- **Formula:** $\text{Total Error} = \text{Bias}^2 + \text{Variance} + \text{Irreducible Error}$
- **Real-World Example:** 
  - *High Bias:* Fitting a straight linear regression line to complex housing price data (underfits).
  - *High Variance:* Fitting a 20th-degree polynomial that hits every training point including noise (overfits).

---

### 76. Data Leakage
- **Definition:** Occurs when information from outside the training dataset (such as target values or future data) accidentally leaks into the model during training, causing artificially high validation metrics that fail in production.
- **Real-World Example:** Scaling features using the mean/variance of the *entire* dataset (train + test) before splitting, or including `Customer_Account_Closed_Date` when predicting customer churn prior to account closure.
- **Prevention:** Perform all preprocessing transformations strictly inside cross-validation folds on training splits only.

---

### 77. Class Imbalance
- **Definition:** A condition where target categories in a classification problem are represented in drastically unequal proportions.
- **Real-World Example:** Credit card fraud detection where 99.9% of transactions are legitimate and only 0.1% are fraudulent.
- **Handling Strategies:** SMOTE (Synthetic Minority Over-sampling), class-weighted loss functions (`scale_pos_weight` in XGBoost), evaluating with PR-AUC / F1-Score instead of Accuracy.

---

### 78. Label Noise
- **Definition:** Inaccuracies, mislabeling, or inconsistencies present within the target variable $y$ of the dataset.
- **Real-World Example:** Crowd-sourced annotation datasets where human annotators misclassify images (e.g., labeling a husky dog as a wolf).
- **Impact & Solutions:** Degrades decision boundaries and causes overfitting. Handled via data cleaning, robust loss functions (e.g., Huber loss), or confident learning algorithms (e.g., Cleanlab).

---

### 79. Data Drift (Covariate Shift)
- **Definition:** A shift in the distribution of input features $P(X)$ over time while the conditional distribution of target output given features $P(Y|X)$ remains constant.
- **Real-World Example:** An income classification model trained on pre-inflation data fails when user income values increase across the board post-inflation, even though high-income logic hasn't changed.
- **Detection:** Kolmogorov-Smirnov (KS) tests or Population Stability Index (PSI).

---

### 80. Concept Drift
- **Definition:** A shift in the underlying relationship between input features and target outputs $P(Y|X)$, meaning the actual logic behind target prediction has changed.
- **Real-World Example:** Prior to 2020, booking a flight months in advance correlated with business travel. During global travel shifts, advance booking behavior lost that correlation.
- **Handling:** Online learning methods, sliding window training on recent data, dynamic retraining.

---

## Category 9: Optimization

---

### 81. Gradient Descent
- **Definition:** An iterative first-order optimization algorithm that minimizes a differentiable loss function by taking steps proportional to the negative gradient at the current point.
- **Formula:** $\theta_{t+1} = \theta_t - \eta \nabla L(\theta_t)$
- **Real-World Example:** Navigating down a foggy mountain by feeling which direction slopes downward most steeply and taking a step in that direction.

---

### 82. Stochastic Gradient Descent (SGD)
- **Definition:** A variant of Gradient Descent that updates model parameters using only **one randomly chosen training sample** per iteration.
- **Real-World Example:** Adjusting self-driving steering controls continuously after evaluating every single sensor reading individually instead of waiting to average a full minute of sensor data.
- **Trade-off:** Extremely fast updates and can escape local minima, but creates high oscillation in the loss landscape.

---

### 83. Mini-Batch Gradient Descent
- **Definition:** An optimization variant that updates parameters using a small batch (e.g., 32, 64, 128 samples) of training data.
- **Real-World Example:** Training a ResNet model on batches of 64 images at a time using GPU matrix parallelization.
- **Why Standard:** It balances the computational stability of Full-Batch GD with the speed and memory efficiency of SGD.

---

### 84. Adam (Adaptive Moment Estimation)
- **Definition:** An adaptive optimization algorithm that combines the concepts of **Momentum** (first moment / mean of gradients) and **RMSProp** (second moment / uncentered variance of gradients).
- **Real-World Example:** Used as the default optimizer for training LLMs and Transformers (e.g., GPT models, BERT) because it adapts learning rates per parameter automatically.

---

### 85. RMSProp
- **Definition:** An adaptive learning rate method that divides the gradient by a running average of its recent magnitude, preventing learning rate decay in non-stationary environments.
- **Real-World Example:** Often used in Recurrent Neural Networks (RNNs) and Reinforcement Learning where gradient scales vary drastically over time.

---

### 86. Momentum
- **Definition:** An optimization technique that accelerates gradient descent by adding a fraction of the previous update vector to the current update step, building up velocity in consistent directions.
- **Real-World Example:** A heavy ball rolling down a bumpy hill; its accumulated momentum helps it roll past small bumps and ravines (local minima/saddle points).

---

### 87. Learning Rate Scheduling
- **Definition:** The strategy of adjusting the learning rate $\eta$ during the training process according to a predefined schedule.
- **Real-World Example:** Cosine Annealing in deep neural networks—starting with a higher learning rate to explore parameter space rapidly, then gradually decaying it to fine-tune near the optimum.

---

### 88. Weight Initialization
- **Definition:** Techniques used to set initial random values of neural network weights to prevent vanishing or exploding gradients during backpropagation.
- **Real-World Example:** 
  - *He/Kaiming Initialization:* Used for layers with ReLU activation.
  - *Xavier/Glorot Initialization:* Used for layers with Sigmoid or Tanh activation.

---

### 89. Early Stopping
- **Definition:** A regularization technique that monitors validation performance during training and halts the process when validation loss stops improving after a specified number of epochs (`patience`).
- **Real-World Example:** Training an image classifier for 100 epochs, but stopping automatically at epoch 23 because validation loss started increasing (signaling overfitting).

---

### 90. Gradient Clipping
- **Definition:** A safety technique that caps or scales gradients to a maximum threshold if their magnitude exceeds a specified limit during backpropagation.
- **Real-World Example:** Prevents numerical instability and NaNs when training deep LSTMs or Recurrent Networks prone to exploding gradients.

---

## Category 10: Linear Models

---

### 91. Linear Regression
- **Definition:** A parametric algorithm that models a continuous target $y$ as a linear combination of input features $X$ plus error.
- **Formula:** $y = X\beta + \epsilon$
- **Real-World Example:** Predicting house prices based on square footage, number of bedrooms, and distance to city center.

---

### 92. Logistic Regression
- **Definition:** A classification model that applies the Sigmoid (logistic) function to a linear combination of features to output probabilities bounded between 0 and 1.
- **Formula:** $P(Y=1|X) = \frac{1}{1 + e^{-X\beta}}$
- **Real-World Example:** Predicting bank loan default (Yes/No) based on credit score, income, and debt-to-income ratio.

---

### 93. Ridge Regression ($L_2$ Regularization)
- **Definition:** Linear regression that adds a penalty proportional to the **squared magnitude** of feature coefficients to the loss function to prevent multicollinearity and overfitting.
- **Penalty:** $\lambda \sum \beta_j^2$
- **Real-World Example:** Predicting healthcare costs when inputs contain highly correlated features (e.g., height, weight, BMI); Ridge shrinks parameters without setting any to zero.

---

### 94. Lasso Regression ($L_1$ Regularization)
- **Definition:** Linear regression that adds a penalty proportional to the **absolute value** of feature coefficients, driving non-essential feature weights strictly to zero.
- **Penalty:** $\lambda \sum |\beta_j|$
- **Real-World Example:** Genomic analysis with 20,000 gene expression features; Lasso eliminates 19,500 irrelevant genes by setting their coefficients to 0 (performing automated feature selection).

---

### 95. Elastic Net
- **Definition:** A regularized regression model that combines both $L_1$ (Lasso) and $L_2$ (Ridge) penalties.
- **Real-World Example:** Used in financial modeling with high-dimensional correlated features; it gets the grouping effect of Ridge combined with the sparsity of Lasso.

---

### 96. Polynomial Regression
- **Definition:** A form of linear regression where the relationship between independent variable $x$ and dependent variable $y$ is modeled as an $n$-th degree polynomial.
- **Real-World Example:** Modeling non-linear biological growth curves (e.g., crop yield vs fertilizer dosage).

---

### 97. Bayesian Regression
- **Definition:** Linear regression formulated with probability distributions over parameters rather than point estimates, yielding predictive uncertainty estimates.
- **Real-World Example:** Clinical trial prediction where domain experts supply prior distributions on drug efficacy, and predictions return explicit confidence bounds.

---

### 98. Quantile Regression
- **Definition:** Regression technique that estimates conditional quantiles (e.g., 10th, 50th, 90th percentile) of the response variable rather than the conditional mean.
- **Real-World Example:** Modeling child growth charts or real estate value risks (predicting the bottom 10% worst-case valuation vs top 10%).

---

### 99. Robust Regression
- **Definition:** Regression designed to overcome limitations of traditional OLS when data contains strong outliers or non-normal errors.
- **Real-World Example:** Huber Loss regression used in sensor telemetry data where occasional hardware spikes would severely distort standard Mean Squared Error lines.

---

### 100. Linear Discriminant Analysis (LDA)
- **Definition:** A supervised technique that projects feature space onto a lower-dimensional axis while maximizing between-class variance relative to within-class variance.
- **Real-World Example:** Facial recognition preprocessing—reducing pixel dimensions while retaining structural boundaries between different individuals.

---

## Category 11: Tree-Based Models

---

### 101. Decision Tree
- **Definition:** A non-parametric model that recursively partitions feature space using orthogonal decision rules based on information gain or Gini impurity.
- **Real-World Example:** A simple loan approval flowchart: "If Credit Score > 700 → Check Income → If Income > $50k → Approve."
- **Pros/Cons:** Highly interpretable, but prone to severe overfitting if unpruned.

---

### 102. Entropy
- **Definition:** A metric measuring the degree of impurity or randomness within a set of class labels.
- **Formula:** $H(S) = -\sum p_i \log_2(p_i)$
- **Real-World Example:** A bag containing 50 red balls and 50 blue balls has maximum entropy (1.0). A bag with 100 red balls has minimum entropy (0.0).

---

### 103. Gini Index (Gini Impurity)
- **Definition:** The probability of incorrectly classifying a randomly chosen element from the set if it was randomly labeled according to class distribution.
- **Formula:** $G = 1 - \sum p_i^2$
- **Interview Note:** Default criterion for CART trees because calculating powers ($p_i^2$) is faster than calculating logarithms in Entropy.

---

### 104. Information Gain
- **Definition:** The expected reduction in entropy achieved by splitting a dataset on a given feature.
- **Real-World Example:** Selecting whether to split customer churn data on "Age" vs "Contract Type"—the tree picks "Contract Type" because it causes a larger decrease in overall entropy.

---

### 105. CART (Classification and Regression Trees)
- **Definition:** A specific decision tree algorithm that produces binary trees, using Gini Impurity for classification and MSE reduction for regression.
- **Real-World Example:** The default underlying tree construction algorithm used in popular libraries like `scikit-learn`.

---

### 106. Random Forest
- **Definition:** An ensemble bagging algorithm that builds a multitude of deep decision trees on bootstrap samples and aggregates their predictions, using random feature subsets at each split.
- **Real-World Example:** Predicting customer churn by training 500 decision trees on random subsets of data and averaging their outputs to reduce overall variance.

---

### 107. Extra Trees (Extremely Randomized Trees)
- **Definition:** An ensemble technique similar to Random Forest, but goes one step further by picking cut-off split thresholds completely **at random** for each feature rather than calculating optimal split points.
- **Real-World Example:** Used when computational speed is paramount on large datasets; trades slight increase in bias for lower variance and much faster training.

---

### 108. AdaBoost (Adaptive Boosting)
- **Definition:** A sequential boosting ensemble where each subsequent model (typically a decision stump) focuses heavily on instances misclassified by preceding models by increasing their sample weights.
- **Real-World Example:** Binary face detection algorithms (e.g., Viola-Jones framework) combining hundreds of fast, weak feature detectors sequentially.

---

### 109. Gradient Boosting
- **Definition:** An ensemble method that builds decision trees sequentially, where each new tree is trained to predict the **pseudo-residuals** (negative gradients of the loss function) of the combined ensemble.
- **Real-World Example:** Estimating insurance claim payouts by sequentially fitting shallow trees to remaining estimation errors.

---

### 110. XGBoost (Extreme Gradient Boosting)
- **Definition:** An optimized gradient boosting library implementing second-order Taylor expansion for loss functions, built-in $L_1/L_2$ regularization, missing value handling, and cache-aware processing.
- **Real-World Example:** Dominated tabular competitions on Kaggle for years due to superior speed and predictive power on structured business data.

---

## Category 12: Advanced Boosting & Ensembles

---

### 111. LightGBM
- **Definition:** A gradient boosting framework developed by Microsoft using **Histogram-based** feature binning and **Leaf-wise** (best-first) tree growth.
- **Real-World Example:** E-commerce recommendation systems handling tens of millions of rows; trains 10x faster than traditional XGBoost with lower memory footprint.

---

### 112. CatBoost
- **Definition:** A gradient boosting algorithm optimized by Yandex for target-based categorical encoding and symmetric (oblivious) decision trees.
- **Real-World Example:** Predicting user click-through rates on ad networks containing high-cardinality categorical variables (e.g., Device ID, Zip Code) without manual one-hot encoding.

---

### 113. Histogram Boosting
- **Definition:** A technique that discretizes continuous numerical features into integer bins (e.g., 256 bins), reducing split evaluation time from $O(N \log N)$ to $O(N_{\text{bins}})$.
- **Real-World Example:** Scikit-learn's `HistGradientBoostingClassifier`, enabling fast tree training on datasets with hundreds of thousands of samples.

---

### 114. Stacking (Stacked Generalization)
- **Definition:** An ensemble technique where predictions from diverse base models (e.g., SVM, Random Forest, XGBoost) are fed as input features to train a higher-level meta-model (e.g., Logistic Regression).
- **Real-World Example:** Winning pipeline architectures in competitive ML where disparate models leverage unique feature spaces and a simple meta-model finds optimal blend weights.

---

### 115. Voting
- **Definition:** An ensemble approach combining outputs from multiple distinct classifiers via **Hard Voting** (majority rule) or **Soft Voting** (averaging predicted probabilities).
- **Real-World Example:** Combining a Naive Bayes classifier, Logistic Regression, and Random Forest for sentiment analysis.

---

### 116. Bagging (Bootstrap Aggregating)
- **Definition:** Parallel ensemble method where multiple estimators are trained independently on different bootstrap samples of dataset and averaged.
- **Objective:** Reduces model **variance** without altering bias.

---

### 117. Boosting
- **Definition:** Sequential ensemble method where weak learners are trained sequentially to correct residual errors made by preceding models.
- **Objective:** Reduces model **bias** substantially.

---

### 118. Blending
- **Definition:** A variation of Stacking where base models are trained on a training set and meta-model predictions are computed on a separate explicit **holdout validation set** rather than out-of-fold predictions.
- **Trade-off:** Simpler to implement than full cross-validated Stacking, but uses less data for meta-model training.

---

### 119. Ensemble Learning
- **Definition:** Meta-paradigm of combining multiple individual machine learning models to improve generalization, stability, and predictive performance beyond any single model.
- **Real-World Example:** Netflix Prize winning solution—combining matrix factorization models, neural networks, and decision trees.

---

### 120. Bootstrap Sampling
- **Definition:** A statistical technique of drawing random samples from a dataset **with replacement**, creating sub-datasets of equal size to the original.
- **Real-World Example:** Given $N$ samples, a bootstrap sample contains roughly $63.2\%$ unique original records, while $36.8\%$ are left out (Out-Of-Bag samples).

---

## Category 13: Distance-Based Models

---

### 121. KNN (K-Nearest Neighbors)
- **Definition:** A non-parametric, instance-based lazy learning algorithm that classifies or regresses a target query point based on majority vote or average of its $k$ nearest neighbors in feature space.
- **Real-World Example:** Recommending movie titles by finding the 5 users with most similar historical ratings to the active user.

---

### 122. Distance Metrics
- **Definition:** Mathematical functions determining non-negative dissimilarity values between vector pairs in multi-dimensional vector space.
- **Properties:** Must satisfy Non-negativity, Identity of Indiscernibles, Symmetry, and Triangle Inequality.

---

### 123. Euclidean Distance ($L_2$ Norm)
- **Definition:** The straight-line distance between two points in Euclidean space.
- **Formula:** $d(x, y) = \sqrt{\sum_{i=1}^n (x_i - y_i)^2}$
- **Real-World Example:** Measuring spatial physical distance between GPS coordinates in 2D plane.

---

### 124. Manhattan Distance ($L_1$ Norm / City Block)
- **Definition:** Sum of absolute differences between vector coordinates.
- **Formula:** $d(x, y) = \sum_{i=1}^n |x_i - y_i|$
- **Real-World Example:** Calculating taxicab travel distance across grid-like city streets (e.g., Manhattan, NYC).

---

### 125. Minkowski Distance
- **Definition:** Generalization of Euclidean ($p=2$) and Manhattan ($p=1$) distance metrics parameterized by $p$.
- **Formula:** $d(x, y) = \left( \sum_{i=1}^n |x_i - y_i|^p \right)^{\frac{1}{p}}$

---

### 126. Cosine Similarity
- **Definition:** Measures directionality rather than magnitude by calculating cosine of angle between two non-zero vectors.
- **Formula:** $\text{Cosine Sim} = \frac{A \cdot B}{\|A\| \|B\|}$
- **Real-World Example:** Comparing document text similarities; two long documents with similar word frequencies have high cosine similarity regardless of text length differences.

---

### 127. KD Tree (k-d Tree)
- **Definition:** A space-partitioning data structure that organizes points in $k$-dimensional space into binary trees for fast spatial retrieval.
- **Real-World Example:** Accelerating KNN searches from $O(N)$ brute-force down to $O(\log N)$ in low dimensions ($D < 20$).

---

### 128. Ball Tree
- **Definition:** Space-partitioning data structure organizing points into nested hyper-spheres (balls).
- **Advantage:** Outperforms KD trees in higher dimensions where rectangular spatial bounding boxes break down due to the curse of dimensionality.

---

### 129. Nearest Neighbor Search
- **Definition:** Optimization task of identifying point(s) in a stored database closest to a query vector based on distance metrics.

---

### 130. Approximate Nearest Neighbor (ANN)
- **Definition:** Algorithmic techniques (e.g., HNSW, FAISS, Annoy) that trade perfect exact recall for orders-of-magnitude faster vector searches in massive vector databases.
- **Real-World Example:** Searching through 100 million vector embeddings in real-time vector search engines (e.g., Pinecone, Milvus, Qdrant).

---

## Category 14: Probabilistic Models

---

### 131. Naive Bayes
- **Definition:** Probabilistic classifier applying Bayes' Theorem with the "naive" assumption that features are conditionally independent given class label.
- **Real-World Example:** Real-time spam filters analyzing word occurrences independently.

---

### 132. Gaussian Naive Bayes
- **Definition:** Naive Bayes variant where continuous feature attributes are assumed to follow normal (Gaussian) distributions within each class.
- **Real-World Example:** Classifying iris flower species based on continuous petal length and width measurements.

---

### 133. Multinomial Naive Bayes
- **Definition:** Naive Bayes variant designed for discrete integer counts (e.g., word frequency counts in text documents).
- **Real-World Example:** Classifying news articles into categories (Sports, Politics, Tech) based on bag-of-words token counts.

---

### 134. Bernoulli Naive Bayes
- **Definition:** Naive Bayes variant designed for binary/boolean features indicating feature presence or absence.
- **Real-World Example:** Document classification based on presence (1) or absence (0) of specific keyword indicators.

---

### 135. Bayesian Learning
- **Definition:** A paradigm of statistical inference where prior probability distributions over parameters are updated using observed data to yield posterior distributions.
- **Real-World Example:** Updating drug safety estimates dynamically as patient outcome data arrives during clinical trials.

---

### 136. Bayes' Theorem
- **Definition:** Mathematical theorem describing conditional probability of an event based on prior knowledge of related conditions.
- **Formula:** $P(A|B) = \frac{P(B|A) P(A)}{P(B)}$
- **Real-World Example:** Calculating probability a patient has a disease given a positive lab test result.

---

### 137. Prior Probability ($P(A)$)
- **Definition:** Unconditional probability assigned to a parameter or hypothesis *before* observing current sample evidence.
- **Real-World Example:** The general prevalence rate of disease in a global population (e.g., 1 in 10,000 people).

---

### 138. Posterior Probability ($P(A|B)$)
- **Definition:** Updated probability of a hypothesis calculated *after* combining prior belief with newly observed data evidence.

---

### 139. Likelihood ($P(B|A)$)
- **Definition:** Probability of observing experimental evidence given that a specific hypothesis is true.
- **Real-World Example:** The probability that a sick patient tests positive on a diagnostic test (test sensitivity).

---

### 140. Maximum Likelihood Estimation (MLE)
- **Definition:** Method of estimating model parameters by selecting values that maximize likelihood function of observed sample data.
- **Real-World Example:** Fitting Gaussian distribution mean and variance to observed heights by finding parameters maximizing joint probability density.

---

## Category 15: Support Vector Machines (SVM)

---

### 141. Support Vector Machine (SVM)
- **Definition:** Supervised algorithm that constructs optimal hyper-planes in high-dimensional space maximizing geometric margin separation between binary classes.
- **Real-World Example:** Image classification, handwriting recognition, and bioinformatics (gene expression classification).

---

### 142. Kernel Trick
- **Definition:** Implicitly mapping low-dimensional non-separable input space into higher-dimensional feature space via dot-product functions without computing explicit high-dimensional coordinates.
- **Formula:** $K(x, z) = \phi(x)^T \phi(z)$

---

### 143. Linear Kernel
- **Definition:** Standard dot-product kernel used when feature space is already linearly separable or dimension count is very large ($D \gg N$).
- **Formula:** $K(x, z) = x^T z$
- **Real-World Example:** Text classification tasks (e.g., TF-IDF sparse matrix classification).

---

### 144. Polynomial Kernel
- **Definition:** Kernel representing interactions between original features up to a designated polynomial degree $d$.
- **Formula:** $K(x, z) = (x^T z + c)^d$

---

### 145. RBF Kernel (Radial Basis Function)
- **Definition:** Non-linear kernel mapping instances into infinite-dimensional Hilbert space based on distance from support vectors.
- **Formula:** $K(x, z) = \exp(-\gamma \|x - z\|^2)$
- **Real-World Example:** Default SVM kernel capable of capturing complex circular or non-linear decision boundaries.

---

### 146. Margin
- **Definition:** Perpendicular distance between decision boundary hyper-plane and closest training points (Support Vectors) from either class.

---

### 147. Soft Margin
- **Definition:** SVM variant introducing parameter $C$ and slack variables ($\xi$) allowing controlled misclassifications to handle noisy or non-linearly separable real data.
- **Trade-off:** High $C$ penalizes mistakes heavily (prone to overfitting); low $C$ allows wider margin (prone to underfitting).

---

### 148. Hard Margin
- **Definition:** Strict SVM requiring full linear separation of all training points with zero allowed misclassifications.
- **Limitation:** Fails if data contains noise, overlap, or non-linearly separable distributions.

---

### 149. Support Vectors
- **Definition:** Critical training data points lying on margin boundary lines that directly define geometric orientation and position of decision hyper-plane.
- **Interview Note:** Removing non-support-vector data points leaves model decision boundary completely unchanged.

---

### 150. Hinge Loss
- **Definition:** Convex loss function used in SVMs that penalizes misclassifications and points within margin boundary.
- **Formula:** $L(y, f(x)) = \max(0, 1 - y \cdot f(x))$

---

## Category 16: Clustering

---

### 151. K-Means Clustering
- **Definition:** Partitioning algorithm grouping data into $K$ clusters by assigning points to nearest centroid and updating centroids to cluster mean iteratively.
- **Real-World Example:** Customer segmentation grouping shoppers into $K=5$ distinct buying personas based on annual spend and visit frequency.

---

### 152. Hierarchical Clustering
- **Definition:** Clustering method constructing nested hierarchy of tree clusters visualized via Dendrogram using **Agglomerative** (bottom-up) or **Divisive** (top-down) strategies.
- **Real-World Example:** Constructing evolutionary phylogenetic trees of biological species based on genetic similarities.

---

### 153. DBSCAN
- **Definition:** Density-based clustering grouping regions of high point density while classifying points in low-density regions as noise/outliers.
- **Real-World Example:** Spatial anomaly detection flagging irregular crime or fraud clusters without prescribing predetermined number of clusters.

---

### 154. Mean Shift
- **Definition:** Non-parametric density gradient estimation updating cluster candidate points toward mode density peaks iteratively using sliding kernel windows.
- **Real-World Example:** Computer vision image segmentation and object tracking.

---

### 155. Gaussian Mixture Models (GMM)
- **Definition:** Probabilistic soft-clustering model assuming data points originate from mixture of finite Gaussian distributions fitted via Expectation-Maximization (EM).
- **Real-World Example:** Modeling complex multimodal distributions where clusters overlap and points require probabilistic membership scores.

---

### 156. Agglomerative Clustering
- **Definition:** Bottom-up hierarchical method starting with each point as its own cluster and merging nearest pairs iteratively based on linkage criteria (Single, Complete, Ward).

---

### 157. Silhouette Score
- **Definition:** Metric measuring how well-separated clusters are by comparing intra-cluster distance ($a$) to nearest neighbor cluster distance ($b$).
- **Formula:** $S = \frac{b - a}{\max(a, b)}$
- **Range:** $[-1, +1]$. High values ($+1$) indicate dense, well-separated clusters.

---

### 158. Elbow Method
- **Definition:** Heuristic determining optimal cluster count $K$ by plotting Within-Cluster Sum of Squares (WCSS) against $K$ values and locating "elbow" inflection point.

---

### 159. Cluster Validation
- **Definition:** Set of techniques evaluating structural validity of clustering results using internal indices (Silhouette, Davies-Bouldin) or external labels (Adjusted Rand Index).

---

### 160. Density-Based Clustering
- **Definition:** Clustering family defining clusters as continuous dense regions separated by low-density areas, capable of identifying arbitrary non-spherical shapes (e.g., DBSCAN, HDBSCAN).

---

## Category 17: Deep Learning

---

### 161. Neural Network
- **Definition:** Computational architecture composed of interconnected artificial neurons organized in input, hidden, and output layers optimized via backpropagation.
- **Real-World Example:** Universal function approximators powering modern speech recognition, vision, and language AI systems.

---

### 162. Perceptron
- **Definition:** The fundamental single-layer artificial neuron evaluating dot product of inputs and weights passed through step function.
- **Limitation:** Can only solve linearly separable problems (fails on basic XOR gate).

---

### 163. Activation Function
- **Definition:** Non-linear mathematical transformation applied to neuron output node sums (e.g., ReLU, Sigmoid, Tanh, GELU) allowing networks to learn complex non-linear patterns.
- **Real-World Example:** **ReLU** ($ \max(0, x) $) prevents vanishing gradients in deep feedforward architectures.

---

### 164. CNN (Convolutional Neural Network)
- **Definition:** Neural network architecture using spatial convolution kernels and pooling layers to extract spatial feature hierarchies.
- **Real-World Example:** Automated X-ray radiology diagnosis, self-driving lane detection, and image classification.

---

### 165. RNN (Recurrent Neural Network)
- **Definition:** Sequential architecture containing feedback loops where hidden states act as internal memory across sequence timesteps.
- **Limitation:** Suffers from severe vanishing/exploding gradients over long sequence steps.

---

### 166. LSTM (Long Short-Term Memory)
- **Definition:** Advanced RNN architecture introducing cell states guarded by **Input**, **Forget**, and **Output** gates to regulate information retention across long time horizons.
- **Real-World Example:** Time-series stock price forecasting and historical machine telemetry anomaly detection.

---

### 167. GRU (Gated Recurrent Unit)
- **Definition:** Streamlined variant of LSTM combining cell state and hidden state using two gates (**Reset** and **Update** gates).
- **Advantage:** Faster training runtime and lower parameter count than standard LSTM with comparable performance.

---

### 168. Transformer
- **Definition:** Deep learning architecture relying completely on **Self-Attention** mechanisms, processing sequence tokens in parallel without recurrence.
- **Real-World Example:** Modern Foundation Models and LLMs (e.g., GPT-4, Claude, Gemini, LLaMA).

---

### 169. Attention Mechanism
- **Definition:** Technique computing dynamic contextual alignment weights across input tokens, allowing models to focus on relevant context regardless of distance.
- **Formula:** $\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$

---

### 170. Autoencoder
- **Definition:** Unsupervised neural network trained to reconstruct input data through constrained bottleneck latent representation (**Encoder** $\to$ Latent Space $\to$ **Decoder**).
- **Real-World Example:** Anomaly detection, image denoising, and non-linear dimensionality reduction.

---

## Category 18: NLP & Computer Vision

---

### 171. Word Embedding
- **Definition:** Dense continuous vector representations of words where geometric proximity reflects semantic and syntactic relationships.
- **Real-World Example:** $V(\text{"King"}) - V(\text{"Man"}) + V(\text{"Woman"}) \approx V(\text{"Queen"})$.

---

### 172. TF-IDF
- **Definition:** Statistical metric assessing relative importance of a word to a document within a broader corpus collection.
- **Formula:** $\text{TF-IDF} = \text{TF}(t, d) \times \log\left(\frac{N}{\text{DF}(t)}\right)$
- **Real-World Example:** Keyword extraction and traditional search engine document ranking.

---

### 173. Word2Vec
- **Definition:** Neural architecture generating static vector embeddings using two shallow training approaches: **CBOW** (predicting target word from context) or **Skip-Gram** (predicting context from target word).

---

### 174. BERT
- **Definition:** Pre-trained Transformer encoder model producing contextualized word embeddings by training bidirectionally on Masked Language Modeling (MLM) and Next Sentence Prediction (NSP).
- **Real-World Example:** Google Search intent understanding and semantic passage retrieval.

---

### 175. Vision Transformer (ViT)
- **Definition:** Architecture applying standard Transformer encoder directly to sequence of flattened, non-overlapping image patches.
- **Real-World Example:** State-of-the-art visual recognition tasks on large-scale datasets (e.g., ImageNet-21k).

---

### 176. Image Classification
- **Definition:** Computer vision task assigning single label from set of predefined categories to entire input image.
- **Real-World Example:** Classifying photo uploads into "Cat", "Dog", or "Car".

---

### 177. Object Detection
- **Definition:** Task identifying multiple distinct target objects within an image, classifying each, and predicting bounding coordinates ($x, y, w, h$).
- **Real-World Example:** YOLO (You Only Look Once) powering real-time pedestrian detection in autonomous vehicles.

---

### 178. Semantic Segmentation
- **Definition:** Pixel-wise computer vision classification labeling every individual image pixel with corresponding class entity category.
- **Real-World Example:** Medical MRI scan segmentation highlighting tumor boundary regions at pixel resolution.

---

### 179. OCR (Optical Character Recognition)
- **Definition:** System converting raster images of typed, handwritten, or printed text into machine-encoded editable text.
- **Real-World Example:** Scanning paper receipts or passports for automated expense reporting apps.

---

### 180. Image Augmentation
- **Definition:** Artificially expanding training dataset size and invariance by applying transformations (cropping, scaling, color jitter, horizontal flips).
- **Real-World Example:** Preventing overfitting in image classifiers by generating modified geometric variants during minibatch loading.

---

## Category 19: Deployment & MLOps

---

### 181. Model Deployment
- **Definition:** Process of integrating trained ML artifacts into production environments to serve live inference requests (via REST endpoints, gRPC, microservices, or batch pipelines).
- **Real-World Example:** Wrapping a Scikit-Learn pipeline inside FastAPI and deploying via Docker onto Kubernetes.

---

### 182. Model Monitoring
- **Definition:** Continuous operational tracking of deployed models evaluating latency, system throughput, error rates, data quality, and predictive decay over time.
- **Real-World Example:** Prometheus and Grafana dashboards tracking drift and prediction latency on production fraud detection endpoints.

---

### 183. Drift Detection
- **Definition:** Automated monitoring pipelines calculating statistical divergence between baseline training distributions and live inference payload features.
- **Real-World Example:** Triggering alerts when Kolmogorov-Smirnov statistical tests identify significant drift in incoming live user feature distributions.

---

### 184. A/B Testing
- **Definition:** Controlled live experimentation routing traffic split between control Model A (legacy) and treatment Model B (candidate) to measure real business metric lift.
- **Real-World Example:** Routing 50% of website users to new recommendation algorithm to measure real conversion rate changes.

---

### 185. CI/CD for ML (CT - Continuous Training)
- **Definition:** Automated workflows governing code testing, data validation, automated retraining, validation checks, and zero-downtime containerized deployments.
- **Real-World Example:** GitHub Actions or GitLab CI triggering training pipeline when new annotated data lands in cloud storage buckets.

---

### 186. Feature Store
- **Definition:** Centralized repository managing feature transformation logic, serving consistent offline features for model training and ultra-low latency online features for live inference.
- **Real-World Example:** Tools like Feast or Hopsworks preventing training-serving skew across engineering teams.

---

### 187. Model Registry
- **Definition:** Central repository managing model lifecycle stages (Staging, Production, Archived), versioning artifacts, performance benchmarks, and lineage audit histories.
- **Real-World Example:** MLflow Model Registry tracking production model binaries alongside training git commits.

---

### 188. Shadow Deployment
- **Definition:** Deployment strategy routing live production traffic to candidate model in parallel with active model without returning candidate predictions to end-user.
- **Real-World Example:** Testing new candidate model performance and latency on real live production workloads with zero user risk.

---

### 189. Canary Deployment
- **Definition:** Deployment strategy incrementally rolling out new model version to small fraction of traffic (e.g., 5%) before full deployment.
- **Real-World Example:** Rolling out updated recommendation model to 5% of app users; monitoring crash/error rates before completing 100% rollout.

---

### 190. Retraining Pipeline
- **Definition:** Automated end-to-end orchestration pipeline triggering data ingestion, feature generation, model retraining, and evaluation on schedule or drift alert.

---

## Category 20: Explainability & Ethics

---

### 191. Explainable AI (XAI)
- **Definition:** Suite of tools and frameworks making complex black-box model decisions transparent, interpretable, and understandable to humans.
- **Real-World Example:** Providing explicit reason codes to loan applicants when credit application models reject their request.

---

### 192. LIME (Local Interpretable Model-agnostic Explanations)
- **Definition:** Technique explaining individual predictions by perturbing sample features locally and fitting simple interpretable surrogate model (e.g., sparse linear regression).
- **Real-World Example:** Explaining why an image classifier identified a specific photo as an electric guitar by highlighting super-pixels influencing the local decision boundary.

---

### 193. SHAP (Shapley Additive exPlanations)
- **Definition:** Game-theoretic approach assigning fair additive feature importance scores based on marginal contributions across all possible feature sub-combinations.
- **Real-World Example:** Quantifying exactly how much age (+$30), income (-$15), and credit score (+$45) contributed to individual insurance pricing outputs.

---

### 194. Fairness in AI
- **Definition:** Engineering practices ensuring models generate equitable decisions without systemic discrimination against protected demographic attributes (e.g., race, gender, age).
- **Real-World Example:** Auditing hiring recommendation algorithms to guarantee Equal Opportunity Difference and Demographic Parity metrics are satisfied.

---

### 195. Bias in AI
- **Definition:** Systematic distortion or unfair decision outputs introduced by historical societal inequalities reflected in training data or biased sampling methodologies.
- **Real-World Example:** Facial recognition models exhibiting higher error rates on darker skin tones due to underrepresentation in training sets.

---

### 196. Privacy in Machine Learning
- **Definition:** Frameworks ensuring individual sensitive identity data within training sets cannot be reconstructed, extracted, or leaked through model attacks.

---

### 197. Federated Learning
- **Definition:** Decentralized training technique fitting local models directly on edge devices (e.g., mobile phones) and aggregating parameter gradients on central server without raw data collection.
- **Real-World Example:** Google Gboard learning next-word keyboard suggestions on user smartphones without uploading private chat logs to central servers.

---

### 198. Differential Privacy
- **Definition:** Mathematical guarantee bounding individual record leakage by injecting calibrated statistical noise into query responses or gradient calculations.
- **Real-World Example:** Census bureau releasing public statistical data updates while mathematically guaranteeing no individual household identity can be isolated.

---

### 199. Responsible AI
- **Definition:** Umbrella governance framework operationalizing AI ethics, transparency, accountability, safety, privacy, and environmental sustainability across the full model lifecycle.

---

### 200. AI Governance
- **Definition:** Institutional framework of organizational policies, risk assessment workflows, regulatory compliance protocols, and oversight committees governing AI deployment.
- **Real-World Example:** Enterprise compliance frameworks ensuring ML models adhere to regulations (e.g., EU AI Act, GDPR).
