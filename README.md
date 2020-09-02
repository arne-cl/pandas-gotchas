# pandas-gotchas

This is a list of gotchas I found in [Pandas](https://pandas.pydata.org/) (the Python data analysis library).

## grouping / aggregation

- [Dropping nuisance columns in groupby is a nuisance #21664](https://github.com/pandas-dev/pandas/issues/21664)
  - Pandas silently drops a column if the chosen aggregation method doesn't work on it.
- [pandas GroupBy columns with NaN (missing) values](https://stackoverflow.com/questions/18429491/pandas-groupby-columns-with-nan-missing-values)
  - Pandas silently drops rows when grouping by a column that contains `NaN`.
  - You can avoid this behaviour by using .`groupby(..., dropna=False)`.


# See also

[Prabhant Sing. Gotchas of Pandas (Pydata Delhi).](https://github.com/prabhant/Talk-Pandas-Gotchas/blob/master/Pandas%20Gotchas.ipynb)
