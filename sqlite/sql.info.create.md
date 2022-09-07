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

### Syntax

```sql
CREATE TABLE <table_name> (
    <column_name_1> <data_type_1> PRIMARY KEY,
    <column_name_2> <data_type_2>,
    ...,
    <column_name_n> <data_type_n>
);
```

### Example

```sql
CREATE TABLE cars (
    id INTEGER PRIMARY KEY,
    model_id INTEGER,
    factory_id INTEGER,
    factory_release_timestamp INTEGER,
    mileage INTEGER
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