# DELETE

## Delete all records

### Syntax

```sql
DELETE FROM <table_name>
```

### Example

```sql
DELETE FROM cars;
```

___

## Delete subset of records

### Syntax

```sql
DELETE FROM <table_name>
WHERE <condition>;
```

### Examples

```sql
DELETE FROM cars
WHERE id = 1;
```

```sql
DELETE FROM cars
WHERE mileage < 1000 AND factory_id = 1;
```

```sql
DELETE FROM cars
WHERE factory_id = 1 OR model_id = 1;
```