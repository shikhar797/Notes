
`OneHotEncoder`

`OneHotEncoder` is a method that transforms categorical integer features into a one-hot representation (also known as "dummy variables") . 

- **How it works**: For each unique category in a column, it creates a _new_ binary column. If a data point belongs to that category, the value in the new column is `1`; otherwise, it is `0` .

 
- **Use in Encoding**: It is particularly useful for nominal data (categories with no intrinsic order, like colors or country names) because it prevents the model from assuming an arbitrary numerical order (e.g., assuming 'red' (0) is less than 'blue' (2)) .



`ColumnTransformer`

`ColumnTransformer` is a more powerful utility used for applying different transformations to different columns of the same dataset simultaneously . 


- **How it works**: It allows you to select specific columns by name or index and apply a designated transformer (like `OneHotEncoder` or a numerical scaler) to only those columns, leaving others untouched or applying different transformations to them .

- **Use in Encoding**: Its primary use is to streamline the data preprocessing pipeline. Instead of manually handling categorical and numerical columns separately, you can use `ColumnTransformer` to apply `OneHotEncoder` to only your categorical columns, and maybe a `StandardScaler` to your numerical columns, all within a single, consistent workflow .



## LabelEncoder vs OrdinalEncoder (VERY IMPORTANT)

|Encoder|Used for|Where|
|---|---|---|
|LabelEncoder|Target variable|y|
|OrdinalEncoder|Ordinal features|X|
|OneHotEncoder|Nominal features|X|

#### LabelEncoder 

LabelEncoder is a method in Sklearn which convert categorical data into numerical data so that it can we understood by machine learning algorithm .
* It should be used in ordinal categorical data and dependent categorical data.

* ordinal categorical data means data with meaning full order such as education level. 
*   ex-> higher education > primary education >no education 

- **Satisfaction Scores:** "Very Dissatisfied," "Dissatisfied," "Neutral," "Satisfied," "Very Satisfied".
- 
- **Economic Status:** "Low," "Medium," "High"


