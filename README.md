# SQL Field Report
Author: [Will James](https://github.com/wct-james)

[![Downloads](https://static.pepy.tech/badge/sql-field-report)](https://pepy.tech/project/sql-field-report)

## About
SQL Field Report is a [polars](https://www.pola.rs/) poward data analysis tool, which summarises the schema of a given dataset. This can be a series of flat files (excel/csv) or tables in a database. It returns a table of analysis with the following columns:

| Column | Description |
| --- | --- |
| Table/File | The table or file of the analysed field 
| Field | The analysed column/field
| Count | The number of records in the table/file
| Populated | For the column/field, how many rows are populated
| Unique | For the column/field, how many unique values are present
| Datatype | Estimated CRM datatype for the column/field
## Installation
To install use pip:
`pip install sql-field-report`

## Usage

SQL Field Report is a [Typer](https://github.com/tiangolo/typer) CLI tool to see the available functions run:

`sql-field-report --help`

```
 Usage: sql-field-report [OPTIONS] COMMAND [ARGS]...

Commands
 mssql-database-report                                      MSSQL Database Report                   
 mysql-database-report                                      MySQL Database Report

MSSQL Database Report

Generate an excel report summarising the data in an MSSQL Database

Args:
│ *    server                TEXT     [default: None] [required]                                                       │
│ *    port                  INTEGER  [default: None] [required]                                                       │
│ *    user                  TEXT     [default: None] [required]                                                       │
│ *    password              TEXT     [default: None] [required]                                                       │
│ *    database_name         TEXT     [default: None] [required]                                                       │
│ *    schema                TEXT     [default: None] [required]                                                       │
│ *    output_file_name      TEXT     [default: None] [required]
```

SQL Field Report can also be used as an importable package in python code:
```python
from sql_field_report import build_dataframe_field_report, read_file

analysis_files = ['file1.xlsx', 'file2.xlsx']

build_dataframe_field_report(
    "Field_Report.xlsx,
    analysis_files,
    read_file,
)

```

## TODO
- Improve SQL read speeds by incorporating [connector-x](https://github.com/sfu-db/connector-x), rather than `pd.read_sql`.