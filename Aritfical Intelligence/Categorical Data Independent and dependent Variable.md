
## 1️⃣ What is _Categorical Data_?

**Categorical data** = data that represents **labels or groups**, not numbers with mathematical meaning.

### Examples:

- Gender → `Male`, `Female`
    
- Color → `Red`, `Blue`, `Green`
    
- City → `Delhi`, `Mumbai`, `Chennai`
    
- Purchased? → `Yes`, `No`
    

Even if categories are written as numbers (like `0`, `1`, `2`), they are **still categories**, not quantities.


## 2️⃣ What is an _Independent Variable_?

**Independent Variable (X)** =  
👉 The **input**, **feature**, or **cause**

This is the data you **give to the model** to make a prediction.

### Example:

Predicting salary based on:

- Age
    
- Education
    
- City
    

All of these are **independent variables**.


## 3️⃣ What is a _Dependent Variable_?

**Dependent Variable (y)** =  
👉 The **output**, **target**, or **effect**

This is what the model **tries to predict**.

### Example:

- Salary
    
- Purchased (Yes / No)
    
- House Price



## 🔑 Key rules to remember (EXAM + INTERVIEW)

1. **Independent variable** = Input (X)
    
2. **Dependent variable** = Output (y)
    
3. **Categorical** = Labels / groups
    
4. Categorical **X** → Encode
    
5. Categorical **y** → Classification
    
6. Numerical **y** → Regression





## 5️⃣ Categorical Independent Variable (Categorical X)

👉 Input feature that is categorical.

### Examples:

|Feature|Type|
|---|---|
|Gender|Categorical Independent|
|City|Categorical Independent|
|Education Level|Categorical Independent|

Example dataset:

|Age|City|Salary|
|---|---|---|
|25|Delhi|40k|
|30|Mumbai|60k|

- `City` → **Categorical Independent Variable**
    
- `Age` → Numerical Independent Variable
    
- `Salary` → Dependent Variable
    

⚠️ ML models **cannot understand text**, so categorical X must be encoded:

- OneHotEncoding
    
- LabelEncoding



## 6️⃣ Categorical Dependent Variable (Categorical y)

👉 Output variable is categorical.

### Examples:

|Problem|y Type|
|---|---|
|Email spam detection|Spam / Not Spam|
|Disease prediction|Yes / No|
|Customer churn|Leave / Stay|

This becomes a **classification problem**.



## 7️⃣ Numerical Dependent Variable (Numerical y)

👉 Output is a number.

### Examples:

|Problem|y Type|
|---|---|
|House price prediction|₹ value|
|Salary prediction|Amount|

This becomes a **regression problem**.