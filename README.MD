# advancedEXASOL

AdvancedEXASOL is an extension of [pyEXASOL](https://github.com/EXASOL/pyEXASOL) library for faster data manipulation using Dask.
<img align="left" width="400" height="100" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d6/Exasol_logo.svg/2560px-Exasol_logo.svg.png">

<html>
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/zeroclipboard/2.3.0/ZeroClipboard.min.js"></script>
  </head>
  <body>
    <!-- Code-Block mit Copy-to-Clipboard-Schaltfläche -->
    <pre><code class="copy-to-clipboard">def add(a, b):
    return a + b</code></pre>
    
    <!-- Skript, das die Copy-to-Clipboard-Schaltfläche aktiviert -->
    <script>
      var copyCode = new ZeroClipboard(document.querySelector('.copy-to-clipboard'));
    </script>
  </body>
</html>

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
- [re](https://docs.python.org/3/library/re.html)

## Usage


AdvancedEXASOL has a class named `Features` which contains all the methods. It also has a script `decorators` which contains the following decorators:

- **ensure_table_exists**: Checks if a table exists before performing any operation
- **ensure_connection**: Ensures that the connection is established before running any operation
- **handle_transactions**: Automatically handles transactions when performing any operation
- **sql_injection_safe**: Sanitizes input strings before running any operation
- **enforce_resource_limits**: Enforces resource limits when performing any operation



## Example

Here is an example of how to use AdvancedEXASOL to create a new table from an existing EXASOL table:

```python
from advancedEXASOL import Features

# Connect to EXASOL
conn = Features.connect('hostname', 'username', 'password')

# Create a new table from an existing EXASOL table
Features.create_table_from_table(conn, 'existing_table', 'new_table', 'column1, column2')

# Disconnect from EXASOL
Features.disconnect(conn)
```

## Documentation

The complete documentation for AdvancedEXASOL can be found [here](https://advancedexasol.readthedocs.io/en/latest/).

## License

AdvancedEXASOL is released under the [MIT License](https://opensource.org/licenses/MIT).

## Contributions

Contributions are welcome! Please open an issue or submit a pull request for any bugs or feature requests.

## Contact

If you have any questions or feedback, please feel free to contact me via email at [example@example.com](mailto:example@example.com).

Thank you for using AdvancedEXASOL!
