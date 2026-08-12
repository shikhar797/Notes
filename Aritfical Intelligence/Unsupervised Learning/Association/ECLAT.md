ECLAT stands for Equivalence Class Clustering and bottom-up Lattice Traversal
It is an improved alternative to the Apriori algorithm by providing better scalability and computational efficiency.

The main difference between the two lies in how they store and search through the data:

- [Apriori](https://www.geeksforgeeks.org/machine-learning/apriori-algorithm/) uses a horizontal format where each transaction is a row and it follows a [breadth-first search](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/) (BFS) strategy. This means it scans the database multiple times to find frequent item combinations.


- ECLAT on the other hand uses a vertical format where each item is linked to a list of transaction IDs (TIDs). It uses a [depth-first search](https://www.geeksforgeeks.org/dsa/depth-first-search-or-dfs-for-a-graph/) (DFS) strategy which requires fewer scans and makes it faster and more memory-efficient.



|Aspect|Apriori|ECLAT|
|---|---|---|
|Data Format|Horizontal (transactions as rows)|Vertical (items linked to transaction IDs)|
|Search Strategy|Breadth-First Search (BFS)|Depth-First Search (DFS)|
|Database Scans|Multiple scans required|Fewer scans needed|
|Memory Efficiency|Less memory-efficient|More memory-efficient|
|Speed|Slower, especially with large datasets|Faster due to vertical representation|


```

from itertools import combinations

# Transactions
transactions = [
    ['Milk', 'Bread', 'Butter'],
    ['Bread', 'Butter'],
    ['Milk', 'Bread'],
    ['Milk', 'Butter'],
    ['Bread', 'Butter', 'Eggs']
]

min_support = 0.4
min_count = int(min_support * len(transactions))

# Convert transactions to vertical format
vertical = {}

for tid, transaction in enumerate(transactions):
    for item in transaction:
        if item not in vertical:
            vertical[item] = set()
        vertical[item].add(tid)

print("Vertical Format:")
for item, tids in vertical.items():
    print(item, tids)


# ECLAT
frequent_itemsets = {}

items = sorted(vertical.keys())

for item in items:
    if len(vertical[item]) >= min_count:
        frequent_itemsets[frozenset([item])] = vertical[item]


def eclat(prefix, items):
    for i in range(len(items)):
        item, tidset = items[i]

        new_itemset = prefix | frozenset([item])

        frequent_itemsets[new_itemset] = tidset

        suffix = []

        for j in range(i + 1, len(items)):
            next_item, next_tidset = items[j]

            intersection = tidset & next_tidset

            if len(intersection) >= min_count:
                suffix.append((next_item, intersection))

        eclat(new_itemset, suffix)


# Prepare frequent single items
initial_items = [
    (item, vertical[item])
    for item in items
    if len(vertical[item]) >= min_count
]

eclat(frozenset(), initial_items)


# Display results
print("\nFrequent Itemsets:")

for itemset, tids in frequent_itemsets.items():
    support = len(tids) / len(transactions)

    print(
        set(itemset),
        "Support:", support,
        "TIDs:", tids
    )
```



```

from pyECLAT import ECLAT

# Transactions
transactions = [
    ['Milk', 'Bread', 'Butter'],
    ['Bread', 'Butter'],
    ['Milk', 'Bread'],
    ['Milk', 'Butter'],
    ['Bread', 'Butter', 'Eggs']
]

# Create ECLAT object
eclat = ECLAT(data=transactions)

# Get frequent itemsets
frequent_itemsets, support = eclat.fit(
    min_support=0.4,
    min_combination=1,
    max_combination=3
)

print(frequent_itemsets)
print(support)
```

