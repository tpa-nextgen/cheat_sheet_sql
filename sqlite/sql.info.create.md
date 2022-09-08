# CREATE

## Basic

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1>,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example

```sql
CREATE TABLE cars (
    id INTEGER,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER
);
```

---

## Primary Key

It is used to identify the rows in the table and ensure their uniqueness.

___Each table can have only one primary key but in can consist of multiple columns.___

### Syntax - single column

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> PRIMARY KEY,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example - single column

```sql
CREATE TABLE cars (
    id INTEGER PRIMARY KEY,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER
);
```

### Syntax - multiple columns

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1>,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>,
    PRIMARY KEY (<key_column_name_1>, <key_column_name_2>, ..., <key_column_name_n>)
);
```

### Example - multiple columns

```sql
CREATE TABLE cars (
    id INTEGER,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER,
    PRIMARY KEY (id, factory_release_timestamp)
);
```

---

## Auto incrementation

Changes the algorithm of `INTEGER PRIMARY KEY` id association. Ensures that the id is greater than any other associated so far, so there is no reusal of values.

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> AUTOINCREMENT,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example

```sql
CREATE TABLE cars (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER
);
```

---

## Foreign keys

Foreign keys are the way to reference primary keys in other tables. While inserting data it will be required that the referenced key value exists for any row in the referenced table.

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1>,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>,
    FOREIGN KEY (column_name_in_current_table_1) REFERENCES <other_table_name_1> (column_name_in_other_table_1),
    FOREIGN KEY (column_name_in_current_table_2) REFERENCES <other_table_name_2> (column_name_in_other_table_2),
    ...,
    FOREIGN KEY (column_name_in_current_table_n) REFERENCES <other_table_name_n> (column_name_in_other_table_n),
);
```

### Example

```sql
CREATE TABLE factories (
    id INTEGER PRIMARY KEY,
    latitude REAL,
    longitude REAL
);
```

```sql
CREATE TABLE car_models (
    id INTEGER PRIMARY KEY,
    model_name TEXT,
    date_of_introduction TEXT
);
```

```sql
CREATE TABLE cars (
    id INTEGER PRIMARY KEY,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER,
    FOREIGN KEY (model_id) REFERENCES car_models (id),
    FOREIGN KEY (factory_id) REFERENCES factories (id)
);
```

## Non-nullable values

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> NOT NULL,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example

```sql
CREATE TABLE car_models (
    id INTEGER,
    model_name TEXT NOT NULL,
    date_of_introduction TEXT NOT NULL
);
```

---

## Default values

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> DEFAULT <value>,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example

```sql
CREATE TABLE cars (
    id INTEGER,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER DEFAULT (unixepoch()),
    mileage INTEGER DEFAULT 0
);
```

## Unique values

Used to ensure that the values of specified column or group of columns are be unique.

Main differences:
|Feature|`PRIMARY KEY`|`UNIQUE`|
|-|-|-|
|Accepts NULL|X|V|
|Can be used multiple times in one table|X|V|

### Syntax - single column

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> UNIQUE,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example - single column

```sql
CREATE TABLE car_models (
    id INTEGER,
    model_name TEXT UNIQUE,
    date_of_introduction TEXT
);
```

### Syntax - multiple columns

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1>,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>,
    UNIQUE (<unique_column_name_1>, <unique_column_name_2>, ..., <unique_column_name_n>)
);
```

### Example - multiple columns

```sql
CREATE TABLE cars (
    id INTEGER,
    model_name TEXT UNIQUE,
    date_of_introduction TEXT,
    UNIQUE (model_name, date_of_introduction)
);
```