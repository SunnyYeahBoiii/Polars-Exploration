# Conclusion

## Data types:

The data type system in Polars are similar to others programming languages, but there's a small difference in Nested data types, which is arrays, structs or lists.

## Series:

Series is a one-dimensional array of data with a data type. This is a column in a DataFrame.

## DataFrame:

DataFrame is a two-dimensional array where each column is a Series.

### Inspect a DataFrame:

There are several methods to inspect a DataFrame:
- `head(n)`: Returns the first n rows.
- `glimpse()`: Returns DataFrame but every column comes into a row, which is very useful for wide DataFrames.
- `tail(n)`: Returns the last n rows.
- `sample(n)`: Returns n random rows.
- `describe()`: Returns the summary statistics of the DataFrame.

## Schema:

Schema is like a dict defining the column data type for each column.

We can create a DataFrame's schema by using `schema` in the construction method.

We can also overrides a DataFrame's schema by using `schema_overrides` in the construction method.

## Data types internals:

Polars uses Apache Arrow to for it's data orientation, which is quite interesting. After looking for some extra information about Apache Arrow, I found that Apache Arrow itself is a data format that optimizes the way data is stored in memory. It's called Arrow Columnar Data or something, it has something to do with standardization and vectorization to optimize the performance of data processing, which is too complicated for me to understand right now :).

## Floating Point Numbers:

This section basically tells that:

- `Nan` is equal to `NaN`
- `NaN` is greater than any non-`NaN` number
- Float numbers operation may result in strange bahavior due to the sign of zero or `NaN`.