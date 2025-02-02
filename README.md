# data_laundry

Your one stop solution for cleaning dirty data in pandas dataframes.

# Features 

1. Automatic column renaming to snake_case 
2. Read from csv, xlsx and parquet files into pandas dataframe
3. Selecting subset of columns from the function call itself
4. Uses `dtype_backend='pyarrow'`
5. Convert dataframe to SQL Server compatible code. This is useful if you don't have `LOAD FILE` privileges on the database

# Usage 

```python
import data_laundry as dl

df = dl.launder("/path/to/file", select_columns="columns to select", **default_pandas_kwargs)
df = dl.launder(df, select_columns="columns to select", **default_pandas_kwargs)

dl.convert_to_sql(
    df,
    table_name="name of sql table",
    output_path="file path where sql code will be written",
    step=1000
)
```

# Installation

```python
pip install data_laundry
```
