# pandas Module Cheatsheet

## Importing
**import pandas**

## Quick Use

### DataFrame
1. DataFrames are 2-dimensional structures (like a grid)
2. Series is 1-dimensional (only a row or column)

**pd.read_csv('/path.csv')**:
Provides lots of ways to access and perform computations on the data

### Accessing a Column
**df[key]**:
Similar to accessing a dictionary, use a key, often times a string, to return
a column's information from the *DataFrame*. What is returned is a *Series*, that
represents a single column or row of a *DataFrame*.

### Series Operationes
**df[key] + df[key]**:
Allows use of operators on data within the series, returning a single Series.
However, the original Series won't be changed without assignment.

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
