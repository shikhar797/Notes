**Apriori** is a **frequent itemset mining algorithm** used in **Association Rule Learning**.  
It is mainly used in **Market Basket Analysis** to find items that are frequently bought together.

![[Confidence for Apriori.png]]

- **Support** → How frequently an item appears in dataset
    
- **Confidence** → Probability that item B is bought when item A is bought
    
- **Lift** → Strength of association between items

```

import pandas as pd
from mlxtend.preprocessing import TransactionEncoder
from mlxtend.frequent_patterns import apriori, association_rules

# Transactions
transactions = [
    ['Milk', 'Bread', 'Butter'],
    ['Bread', 'Butter'],
    ['Milk', 'Bread'],
    ['Milk', 'Butter'],
    ['Bread', 'Butter', 'Eggs']
]

# Convert transactions into one-hot encoded format
te = TransactionEncoder()
te_array = te.fit(transactions).transform(transactions)

df = pd.DataFrame(te_array, columns=te.columns_)

print("Transaction Data:")
print(df)

# Find frequent itemsets
frequent_itemsets = apriori(
    df,
    min_support=0.4,
    use_colnames=True
)

print("\nFrequent Itemsets:")
print(frequent_itemsets)

# Generate association rules
rules = association_rules(
    frequent_itemsets,
    metric="confidence",
    min_threshold=0.6
)

print("\nAssociation Rules:")
print(rules[['antecedents', 'consequents', 'support',
             'confidence', 'lift']])
```