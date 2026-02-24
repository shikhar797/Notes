# 📌 Agglomerative Hierarchical Clustering – Short Notes

## 1️⃣ Definition

Agglomerative Hierarchical Clustering is a **bottom-up clustering algorithm** where each data point starts as an individual cluster and pairs of clusters are merged step-by-step until only one cluster remains.

---

## 2️⃣ Type

- Unsupervised Learning
    
- Hierarchical Clustering
    
- Bottom-Up Approach
    

---

## 3️⃣ Key Idea

Start with **N clusters (each point is one cluster)**  
Merge closest clusters repeatedly  
Continue until:

- One cluster remains OR
    
- Required number of clusters (k) is formed
    

---

## 4️⃣ Algorithm Steps

1. Start with each data point as a separate cluster.
    
2. Compute distance matrix.
    
3. Merge the two closest clusters.
    
4. Update distance matrix.
    
5. Repeat until stopping condition.
    

---

## 5️⃣ Linkage Methods (Very Important)

These decide how distance between clusters is calculated:

### 🔹 Single Linkage

Distance between closest points of two clusters.

### 🔹 Complete Linkage

Distance between farthest points.

### 🔹 Average Linkage

Average distance between all pairs.

### 🔹 Ward’s Method

Minimizes variance within clusters.

---

## 📊 Dendrogram (Very Important Concept)

![https://miro.medium.com/0%2AR8acBZk1JrLw4Hg1.png](https://miro.medium.com/0%2AR8acBZk1JrLw4Hg1.png)

![https://uc-r.github.io/public/images/analytics/clustering/hierarchical/unnamed-chunk-13-1.png](https://uc-r.github.io/public/images/analytics/clustering/hierarchical/unnamed-chunk-13-1.png)

![https://ars.els-cdn.com/content/image/3-s2.0-B9780124157811000091-f09-04-9780124157811.jpg](https://ars.els-cdn.com/content/image/3-s2.0-B9780124157811000091-f09-04-9780124157811.jpg)


- Tree-like diagram
    
- Shows how clusters merge
    
- Used to decide optimal number of clusters
    
- Cut horizontally to get k clusters
    

---

## 6️⃣ Advantages

✔ No need to specify k initially  
✔ Dendrogram gives hierarchy  
✔ Works well for small datasets

---

## 7️⃣ Disadvantages

❌ Computationally expensive (O(n³) worst case)  
❌ Not suitable for large datasets  
❌ Once merged, cannot undo

---

## 8️⃣ Use Cases

- Gene sequence analysis
    
- Customer segmentation
    
- Document clustering
    
- Image segmentation