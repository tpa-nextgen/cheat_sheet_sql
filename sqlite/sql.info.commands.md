# Dot Commands

These commands ___are not part___ of SQL statements.
They can be used in [SQLite CLI program (sqlite3)](https://www.sqlite.org/cli.html) and are specific to that application.

Here is a list of the most common commands:
|Command|Description|
|-|-|
|`.help`|Displays a list of all available dot commands|
|`.quit`|Exits the program|
|`.open <filename>`|Close existing database and reopen \<filename\>|
|`.tables`|List names of tables in the current database|
|`.schema <table_name>`|Show the CREATE statement used for \<table_name\> creation|
|`.headers <on\|off>`|Turn display of headers on or off|
|`.mode <mode>`|Set output mode for query results|

## More info on commands

### .mode

Available modes for `.mode` command:
- ascii
- box
- csv
- column
- html
- insert
- json
- line
- list
- markdown
- quote
- table
- tabs
- tcl