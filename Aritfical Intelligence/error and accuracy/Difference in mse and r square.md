## 1️⃣ MSE (Mean Squared Error)

**What it does:**  
MSE tells you **how wrong your model’s predictions are on average**.

### In simple words

- Take the difference between **actual value** and **predicted value**
    
- **Square it** (so negative errors don’t cancel positives)
    
- Average all of them
    

### Why squaring?

- Bigger mistakes get **punished more**
    
- Makes the model care a lot about large errors
    

### Interpretation

- **Lower MSE = better model**
    
- **0 MSE = perfect predictions**
    
- Unit is **squared** (e.g., if output is in meters → MSE is in m²)
    

### Example

Actual: `[3, 5, 7]`  
Predicted: `[2, 5, 10]`

Errors: `[-1, 0, 3]`  
Squared: `[1, 0, 9]`  
MSE = `(1 + 0 + 9)/3 = 3.33`

➡️ Model is _somewhat off_, especially on the last value.

---

## 2️⃣ R² Score (R-square / Coefficient of Determination)

**What it does:**  
R² tells you **how well your model explains the data**.

### Think of it like this

> “How much better is my model than just predicting the average?”

### Range

- **1.0** → perfect model
    
- **0.0** → no better than predicting the mean
    
- **< 0** → worse than a useless model 😬
    

### Interpretation

- `R² = 0.85` → model explains **85% of the variance** in the data
    
- Higher is better
    

### Example

If house prices vary a lot and:

- Your model captures most of that variation → **high R²**
    
- Your model misses trends → **low R²**
    

---

## 🔥 Key Difference (This is important)

|Metric|Measures|Best Value|Scale|
|---|---|---|---|
|**MSE**|Average prediction error|**0**|Unbounded|
|**R²**|Goodness of fit|**1**|≤ 1|

---

## 🧠 When to use what?

- **Training a model** → use **MSE** (or RMSE) as loss
    
- **Evaluating & comparing models** → look at **R²**
    

---

## 🧪 In Python (sklearn)

`from sklearn.metrics import mean_squared_error, r2_score  mse = mean_squared_error(y_true, y_pred) r2  = r2_score(y_true, y_pred)`

---

### TL;DR (exam-friendly 😌)

- **MSE**: “How far off are my predictions?”
    
- **R²**: “How well does my model explain the data?”
    


and one more important thing accuracy_score is for classification where as r square and mean square error (mse) is for regression