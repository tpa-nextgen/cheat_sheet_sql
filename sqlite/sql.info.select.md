# SELECT

## Read all

### Syntax

```sql
SELECT * FROM <table_name>;
```

### Example

```sql
SELECT * FROM car_models;
```

____

## Read specific columns

### Syntax

```sql
SELECT <column_name_1>, <column_name_2>, ..., <column_name_n> FROM <table_name>;
```

### Example

```sql
SELECT id, model_id FROM cars;
```

____

## Read filtered

### Syntax

```sql
SELECT * FROM <table_name> WHERE <condition>;
```

### Example

```sql
SELECT * FROM cars WHERE mileage > 10000;
```

____

## Read ordered

### Syntax

```sql
SELECT * FROM <table_name> ORDER BY <column_name_1> [ASC/DESC], <culumn_name_2>, ..., <column_name_n> [ASC/DESC];
```

### Examples

```sql
SELECT * FROM cars ORDER BY mileage, factory_id;
```

```sql
SELECT * FROM cars ORDER BY mileage DESC, factory_id ASC;
```

____

## Read with limits

### Syntax

```sql
SELECT * FROM <table_name> LIMIT <max_number_records_to_be_returned> [OFFSET <inclusive_offset_to_start_from>];
```

If `OFFSET <inclusive_offset_to_start_from>` part is omitted, the results are returned starting at the begining.

### Examples

```sql
SELECT * FROM cars LIMIT 3;
```

```sql
SELECT * FROM cars LIMIT 5 OFFSET 10;
```
____

## Reading from multiple tables

### Syntax

- Reading data from all tables:
    ```sql
    SELECT * FROM <table_name_1>, <table_name_2>, ..., <table_name_n> WHERE <condition>;
    ```

- Reading all data from specific table:
    ```sql
    SELECT <table_name_x>.* FROM <table_name_1>, <table_name_2>, ..., <table_name_n> WHERE <condition>;
    ```

- Reading specific columns from tables:
    ```sql
    SELECT <table_name_x1>.<x1_column_name>, <table_name_x2>.<x2_column_name>, ..., <table_name_xn>.<xn_column_name> FROM <table_name_1>, <table_name_2>, ..., <table_name_n> WHERE <condition>;
    ```

### Examples

- Reading data from both tables:
    ```sql
    SELECT * FROM cars, car_models WHERE cars.model_id = car_models.id AND car_models.model_name = "Vitz";
    ```

- Reading data just from the ___cars___ table:
    ```sql
    SELECT cars.* FROM cars, car_models WHERE cars.model_id = car_models.id AND car_models.model_name = "Vitz";
    ```

- Reading specific data from tables:
    ```sql
    SELECT cars.id, car_models.model_name, cars.mileage FROM cars, car_models WHERE cars.model_id = car_models.id AND car_models.model_name = "Vitz";
    ```

____

## Join

More convenient way to read from multiple tables is to use `JOIN` keywords.

### Syntax

```sql
SELECT * FROM <table_name_1>
JOIN <table_name_2> ON <table_name_1>.<column_name_2> = <table_name_2>.<foreign_column_name>
JOIN <table_name_3> ON <table_name_1>.<column_name_3> = <table_name_3>.<foreign_column_name>
...
JOIN <table_name_n> ON <table_name_1>.<column_name_n> = <table_name_n>.<foreign_column_name>;
```

### Example

```sql
SELECT * FROM cars JOIN car_models ON cars.model_id = car_models.id;
```

___

## Inner join

### Syntax

```sql
SELECT * FROM <table_name_1>
INNER JOIN <table_name_2> ON <table_name_1>.<column_name_2> = <table_name_2>.<foreign_column_name>
INNER JOIN <table_name_3> ON <table_name_1>.<column_name_3> = <table_name_3>.<foreign_column_name>
...
INNER JOIN <table_name_n> ON <table_name_1>.<column_name_n> = <table_name_n>.<foreign_column_name>;
```

### Example
```sql
SELECT * FROM cars INNER JOIN car_models ON cars.model_id = car_models.id;
```

____

## Left join

### Syntax

```sql
SELECT * FROM <table_name_1>
LEFT JOIN <table_name_2> ON <table_name_1>.<column_name_2> = <table_name_2>.<foreign_column_name>
LEFT JOIN <table_name_3> ON <table_name_1>.<column_name_3> = <table_name_3>.<foreign_column_name>
...
LEFT JOIN <table_name_n> ON <table_name_1>.<column_name_n> = <table_name_n>.<foreign_column_name>;
```

### Example

```sql
SELECT * FROM cars LEFT JOIN car_models ON cars.model_id = car_models.id;
```