# Pandas
- [Indexing and selecting data](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html)
- [Using iloc, loc, & ix](https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/)
- Iterating Dataframes
  - [iterrows](https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iterrows.html)
  - [itertuples](https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.itertuples.html)
  - [iteritems](https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iteritems.html)

## Display all Columns in Jupyter Notebook
```python
pd.options.display.max_columns = None
```

## Filter nan Values
`nan == nan` is always `false`. That is why we can not use `==` to check
for `nan`-values. Use `pd.isnull(obj : scalar or array-like)` instead or
`isnull()`. Examples:
``` python
df.loc[pd.isnull(df['col'])]
df[df['col'].isnull()]
```

## Load and save

### Save to CSV
Here without row names (index) `index=False`.
``` python
df.to_csv(<path_or_buffer>, index=False)
```
also see: <https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html>

### Load from CSV
``` python
df = pd.read_csv(
        <path_or_buffer>,
        sep=';',
        encoding='us-ascii',
        usecols=<col_list>,
        nrows=<number_of_rows_to_read>,
        )
```
