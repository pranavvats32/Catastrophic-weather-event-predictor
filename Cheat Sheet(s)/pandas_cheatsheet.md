# Pandas Cheatsheet

N. P. O'Donnell, 2020

## Importing the Library

```
import pandas as pd
```

## Dataframes

### Reading In Dataframes

From .csv:

```
df = pd.read_csv("data.csv")
```

### Viewing / Chopping up Dataframes

*As run in python REPL. All commands return a dataframe*

Summarized view:

```
df
```

Length of `df`:

```
len(df)
```

First few rows:

```
df.head()
```

Last few rows:

```
df.tail()
```

First 17 rows:

```
df.head(17)
```

Last 21 rows:

```
df.tail(21)
```

Single column:

```
df["column-name"]
```

Multiple columns:

```
df[["column-name-1", "column-name-2"]]
```

Single row at index i:

```
df[i:i+1]
```

Multiple rows at indices in range [4, 10):

*Returns rows 4, 5, 6, 7, 8 and 9*

```
df[4:10]
```

Cherry-pick rows based on index:

*Returns rows 2, 7, 11 and 12*
```
df.loc[[2, 7, 11, 12]]
```

Multiple rows at indices in range[4, 10) with specific columns:

*Returns `column-name-1` column in rows 4, 5, 6, 7, 8 and 9*

```
df.loc[4:10, "column-name-1"]
```

Cherry-pick rows based on index with specific columns:

*Returns `column-name-1` and `column-name-2` columns from rows 2, 7, 11 and 12*
```
df.loc[[2, 7, 11, 12], ["column-name-1", "column-name-2"]]
```

### Convert Dataframe to 2D List

```
df.values.tolist()
```

### Accessing Cells

*As run in python REPL. All commands return a primitive*

Return cell in row 7, column `column-name-3`:

```
df.at[7, "column-name-3"] # Note square brackets!
```

### Column Names

Get alll column names as numpy array:

```
df.columns.values
```

## Data Selection

To select a subset of rows from a dataframe, a list of booleans with equal length to the number of rows of the dataframe can be used. For example if `df` has 5 rows, the following will return a dataframe with rows 0, 1 and 3:

```
df[[True, True, False, True, False]]
```

A dataframe can be compared to a primitive using standard comparison operators such as `=`, `!=`, `<`, `>`, etc. This causes each row of the dataframe to be compared to the primitive resulting in a boolean array with length equal to the number of rows:

```
df["column-name-2"] > 10
```

or

```
df[["column-name-1", "column-name-2", "column-name-3"]] == ["a", "b", "c"]
```

Bringing this together, selections based on predicates can be made:

```
df[df["column-name-2"] > 10]
```

## Aggregates

```
df["column-name"].count()
df["column-name"].min()
df["column-name"].max()
df["column-name"].mean()
df["column-name"].std()
df["column-name"].median()
df["column-name"].mode()
```

## Sampling

Sampling is done with the `.sample()` function. Replacement is off by default.

Random sample of 1 row:

```
df.sample()
```

Random sample of 5 rows:

```
df.sample(5)
```

Random sample of 5000 rows with replacement:

```
df.sample(5000, replace=True)
```

Random sample of 5% with replacement:

```
df.sample(frac=0.05, replace=True)
```

Shuffle a dataframe:

```
df.sample(frac=1.0)
```