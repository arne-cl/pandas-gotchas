# pandas-gotchas

This is a list of gotchas I found in [Pandas](https://pandas.pydata.org/) (the Python data analysis library).

## grouping / aggregation

- [Dropping nuisance columns in groupby is a nuisance #21664](https://github.com/pandas-dev/pandas/issues/21664)
  - Pandas silently drops a column if the chosen aggregation method doesn't work on it.
- [pandas GroupBy columns with NaN (missing) values](https://stackoverflow.com/questions/18429491/pandas-groupby-columns-with-nan-missing-values)
  - Pandas silently drops rows when grouping by a column that contains `NaN`.
  - You can avoid this behaviour by using .`groupby(..., dropna=False)`.
  
## membership in series

- [How to determine whether a Pandas Column contains a particular value](https://stackoverflow.com/questions/21319929/how-to-determine-whether-a-pandas-column-contains-a-particular-value)
  - `x in series` tells you if `x` is in the `index` of `series`
  - use `x in series.values` to check if `x` is in the actual `series`

## filter series / column by substring

To check which elements of a column start with the prefix `field_`,  
run `df.my_column.str.startswith('field_')`. To avoid the error  
`ValueError: Cannot mask with non-boolean array containing NA / NaN values`,  
simply add `na=False` (which will ignore NA values):

```
df.my_column.str.startswith('field_', na=False)
```

# See also

[Prabhant Sing. Gotchas of Pandas (Pydata Delhi).](https://github.com/prabhant/Talk-Pandas-Gotchas/blob/master/Pandas%20Gotchas.ipynb)
