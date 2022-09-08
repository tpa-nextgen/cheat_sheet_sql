# ALTER

## Renaming table

### Syntax

```sql
ALTER TABLE <table_name> RENAME TO <new_table_name>;
```

### Example

```sql
ALTER TABLE factories RENAME TO car_factories;
```

---

## Renaming column

### Syntax

```sql
ALTER TABLE <table_name> RENAME COLUMN <column_name> TO <new_column_name>;
```

### Example

```sql
ALTER TABLE car_models RENAME COLUMN model_name TO name;
```

---

## Adding column

### Syntax

```sql
ALTER TABLE <table_name> ADD COLUMN <column_name> <column_type>;
```

### Example

```sql
ALTER TABLE factories ADD COLUMN number_of_offices INTEGER;
```

---

## Removing column

### Syntax

```sql
ALTER TABLE <table_name> DROP COLUMN <column_name>;
```

### Example

```sql
ALTER TABLE car_models DROP COLUMN date_of_introduction;
```