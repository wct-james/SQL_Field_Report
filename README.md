# SQL Field Report

## Installation
To install use pip:
`pip install sql-field-report`

## Usage

SQL Field Report is a [Typer](https://github.com/tiangolo/typer) CLI tool to see the available functions run:

`sql-field-report --help`

```
MSSQL Database Report

Generate an excel report summarising the data in an MSSQL Database

Args:
    server (str): The SQL server name
    port (int): The SQL server port
    user (str): Your SQL Server username
    password (str): Your SQL Server password
    database_name (str): The name of the database to analyse
    output_file_name (str): The output file name of the report
```