Pandas
======

- https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html
- https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/

Save to CSV
-----------

Here without row names (index) `index=False`.

.. code:: python

   df.to_csv('<path_or_buf>', index=False)

also see: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html

Filter nan Values
-----------------

`nan == nan` is always `false`. That is why we can not use `==` to check for `nan`-values. Use `pd.isnull(obj : scalar or array-like)` instead or `isnull()`. Examples:

.. code:: python

   df.loc[pd.isnull(df['col'])]
   df[df['col'].isnull()]

Iterating Dataframes
--------------------

- https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iterrows.html
- https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.itertuples.html
- https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iteritems.html

Remove duplicate Entries
------------------------

...
