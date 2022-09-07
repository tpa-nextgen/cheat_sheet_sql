# UPDATE

## Update all records

### Syntax

```sql
UPDATE <table_name>
SET <column_name_1> = <value_1>,
    <column_name_2> = <value_2>,
    ...
    <column_name_n> = <value_n>;
```

### Example

```sql
UPDATE cars
SET mileage = 0;
```

```sql
UPDATE cars
SET mileage = 0,
    factory_release_timestamp = 0;
```

___

## Update subset of records

### Syntax

```sql
UPDATE <table_name>
SET <column_name_1> = <value_1>,
    <column_name_2> = <value_2>,
    ...
    <column_name_n> = <value_n>
WHERE <condition>;
```

### Examples

```sql
UPDATE cars
SET mileage = 10000
WHERE id = 1;
```

```sql
UPDATE cars
SET mileage = 1000
WHERE mileage < 1000 AND factory_id = 1;
```

```sql
UPDATE cars
SET mileage = 5000
WHERE factory_id = 1 OR model_id = 1;
```