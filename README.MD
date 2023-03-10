# advancedEXASOL

AdvancedEXASOL is a Python library that extends the functionality of [pyEXASOL](https://github.com/EXASOL/pyEXASOL) and allows for faster data manipulation using Dask. It includes features such as table management, data importing/exporting, and data merging. It also includes various decorators to ensure safe and efficient execution of SQL queries.

The AdvancedEXASOL library contains all the methods and has "decorators" which includes following: ensure_table_exists, ensure_connection, handle_transactions, sql_injection_safe, and enforce_resource_limits. These decorators are used to add additional functionality and safety measures to the methods in the AdvancedEXASOL class.

One of the main features of AdvancedEXASOL is the ability to create a new table from a external source like a Dask DataFrame or an existing EXASOL table using the create_table_from_df and create_table_from_table methods, respectively. It also has the ability to convert an EXASOL table to various formats, such as JSON, CSV, XML, and Excel, using the to_json, to_csv, to_xml, and to_excel methods.

In addition, AdvancedEXASOL allows for data to be imported and exported to and from Dask Dataframes using the import_from_dask and export_to_dask methods. This can be useful for interacting with larger datasets that may not fit in memory.

Finally, AdvancedEXASOL has the ability to merge two tables using the merge_tables method or merge two tables from external sources using the merge_from_external method. This allows for easy data consolidation and management.

Overall, AdvancedEXASOL aims to streamline the interaction between Python and the EXASOL database by providing a wide range of useful features and safety measures.

## Features

AdvancedEXASOL includes the following features:

- **create_table_from_df**: Create a new table from a Pandas Dataframe
- **create_table_from_table**: Create a new table from an existing EXASOL table
- **export_to_dask**: Export data from EXASOL to Dask Dataframe
- **import_from_dask**: Import data from Dask Dataframe to EXASOL
- **to_pandas**: Convert an EXASOL table to Pandas Dataframe
- **to_json**: Convert an EXASOL table to JSON format
- **to_csv**: Convert an EXASOL table to CSV format
- **csv_to_excel**: Convert an EXASOL CSV to an Excel file
- **to_xml**: Convert an EXASOL table to XML format
- **to_excel**: Convert an EXASOL table to an Excel file
- **merge_tables**: Merge two EXASOL tables
- **merge_from_external**: Merge two tables from external sources

## Requirements

AdvancedEXASOL requires the following modules:

- [pyEXASOL](https://github.com/EXASOL/pyEXASOL)
- [dask.dataframe](https://docs.dask.org/en/latest/dataframe.html)
- [Pandas](https://pandas.pydata.org/)
- [xlwt](https://pypi.org/project/xlwt/)

## Usage


AdvancedEXASOL has a class named `Features` which contains all the methods. It also has a script `decorators` which contains the following decorators:

- **ensure_table_exists**: This decorator is used to check if a table exists in the EXASOL database before performing any operation on it. If the table does not exist, an error is raised. This is useful for ensuring that the desired table is available for use before trying to perform any actions on it.
- **ensure_connection**: This decorator is used to ensure that a connection to the EXASOL database has been established before running any operation. If a connection has not been established, an error is raised. This is useful for preventing operations from being run without a valid connection to the database.
- **handle_transactions**: This decorator is used to automatically handle transactions when performing any operation on the EXASOL database. Transactions allow multiple related SQL statements to be executed as a single unit of work, either all succeeding or all being rolled back if any of the statements fail. This decorator ensures that transactions are properly started and ended for each operation, helping to ensure the integrity of the data in the database.
- **sql_injection_safe**: This decorator is used to sanitize input strings before running any operation on the EXASOL database. SQL injection is a type of security vulnerability that occurs when an attacker is able to send malicious code to a database through user input. This decorator helps to prevent such attacks by ensuring that input strings are properly escaped and validated before being used in an operation.
- **enforce_resource_limits**: This decorator is used to enforce resource limits when performing any operation on the EXASOL database. Resource limits can be used to prevent certain operations from consuming too many resources, such as memory or CPU time, which could negatively impact the performance of the database. This decorator helps to ensure that resource limits are properly enforced for each operation, helping to maintain the performance and stability of the database.



## Example

Here is an example of how to use advancedEXASOL:

###### <sub>Connect to the Exasol database</sup>
```python
from advanced_exasol import Features

# Connect to EXASOL
conn = Features.connect('hostname', 'username', 'password')
```
###### <sub>Export to a dask dataframe and import from a dask dataframe via HTTP transport</sup>
```python
# Export data from EXASOL to Dask Dataframe
df = conn.export_to_dask('existing_table')

# Import data from Dask Dataframe to EXASOL
conn.import_from_dask(df, 'new_table')

# Disconnect from EXASOL
conn.close()
```
###### <sub>Different methods to convert data from Exasol to other formats.</sup>
```python
# Convert EXASOL table to Pandas Dataframe
df = conn.to_pandas('existing_table')

# Convert EXASOL table to JSON
json_string = conn.to_json('existing_table')

# Convert EXASOL table to CSV
conn.to_csv('existing_table', 'existing_table.csv')

# Convert EXASOL CSV to Excel file
conn.csv_to_excel('existing_table.csv', 'existing_table.xls')

# Convert EXASOL table to XML
xml_string = conn.to_xml('existing_table')

# Convert EXASOL table to Excel file
conn.to_excel('existing_table', 'existing_table.xls')

# Disconnect from EXASOL
conn.close()
```
###### <sub>Merge data from one table to another. It also supports simple select statements and CTEs.</sup>
```python
# Connect to EXASOL
conn = Features.connect('hostname', 'username', 'password')

# Merge two EXASOL tables
conn.merge_tables('table1', 'table2', 'merged_table', 'column1, column2')

# Disconnect from EXASOL
conn.close()
```
###### <sub>Merge data from different data sources into the database..</sup>
```python
# Connect to EXASOL
conn = Features.connect('hostname', 'username', 'password')

# Merge two tables from external sources
conn.merge_from_external('/path/to/table1.csv', '/path/to/table2.xls', 'merged_table', 'column1, column2')

# Disconnect from EXASOL
conn.close()
```


## Documentation

The complete documentation for pyEXASOL can be found [here](https://github.com/exasol/pyexasol/tree/master/docs).

## License

AdvancedEXASOL is released under the [MIT License](https://opensource.org/licenses/MIT).

## Contributions

Contributions are welcome! Please open an issue or submit a pull request for any bugs or feature requests.

## Contact

If you have any questions or feedback, please feel free to contact me via email at [dfrigewski@gmail.com](mailto:dfrigewski@gmail.com).

Thank you for using AdvancedEXASOL!
