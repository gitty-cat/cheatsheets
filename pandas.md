# pandas Module Cheatsheet

## Importing

**import pandas**

## Quick Use

### DataFrame
1. DataFrames are 2-dimensional structures (like a grid)
2. Series is 1-dimensional (only a row or column)

**df = pd.read_csv('/path.csv')**:
Provides lots of ways to access and perform computations on the data.
Creates a DataFrame object that can be then accessed.

### Accessing a Column

**df[key]**:
Similar to accessing a dictionary, use a key, often times a string, to return
a column's information from the *DataFrame*. What is returned is a *Series*, that
represents a single column or row of a *DataFrame*.

### Series Operations

**df[key] + df[key]**:
Allows use of operators on data within the series, returning a single Series.
However, the original Series won't be changed without assignment.

**df[key] + element**
Applies the operator uniformly across the Series.

### Filtering Data

**df2 = df1[df1[key] bool_stat]**:
Allows only the conditional information to filter the Series out of the DataFrame.

#### Mask
Masks allow the use of a boolean Series as an inexer to grab all the rows or
columns specified.

variable = df[key] conditional

#### Filtering on Multiple Conditions

Using filtering comes with precedence (order of operations). Ergo, it's
important to use parantheses to declare proper order of operations.

(conditional 1) | (conditional 2)

- **&**: 
AND operator that combines two masks 

- **|**:
OR operator that combines two masks

- **~**:
NOT operator of a single mask

### Location

The loc property allows for specification a row indexer and a column indexer to
locate elements and access values.
- If both the row and column indexers are single value, a single value is returned
- If only one of the row or column indexers is a single value, returns a Series
- If neither the row and column indexers are single values, returns a DataFrame

**df.loc[row_indexer, column_indexer]**:
Uses the row and column indexer (which can also be Series keys) to access
desired values. 

**df.loc[[x, y, z], :]]**:
Lists or slices of values are accepted as indexers

**: (for everything)**
When used as an indexer, the ":" will default to all values available

### Group By
The groupby function allows a specific value to be chosen, and then aggregate
another based upon that value as a filter. Best used for when you want to
separate your data into groups to get some value for each one.

**df.groupby(by=key)[aggr_val].sum()**
The .groupby(key) tells the DataFrame we want to group all of its rows by
the key attribute. The function .sum() at the end can be replaced by other
pandas functions such as min, max, and mean.

### Apply
Allows functions to be passed into pandas to transform a value and apply it
to each element in a Series

**def function(param):
    pass**

**df['name'].apply(function)**
Takes the function and returns the values from the calculations of function.
This information must be saved or overwritten.

## Functions

**mean()**:
Calculates the average value of the Series

**min()**:
Calculates the minimum value of the Series

**max()**:
Calculates the maximum value of the Series

**idxmin**:
Calculates the index of the minimum value of the Series

**idxmax**:
Calculates the index of the maximum value of the Series

**count()**:
Calculates the number values in the Series

**unique()**:
Reurns a new Series with all the unique values from the Series
