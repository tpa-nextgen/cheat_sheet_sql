# INSERT

## Inserting single value

### Syntax

```sql
INSERT INTO <table_name> VALUES (<column_1_value>, <column_2_value>, ..., <column_n_value>);
```

### Example

```sql
INSERT INTO car_models VALUES (1, "Vitz", "1999");
```

____

## Inserting multiple values

### Syntax

```sql
INSERT INTO <table_name> VALUES
    (<column_1_value_1>, <column_2_value_1>, ..., <column_n_value_1>),
    (<column_1_value_2>, <column_2_value_2>, ..., <column_n_value_2>),
    ...,
    (<column_1_value_n>, <column_2_value_n>, ..., <column_n_value_n>);
```

### Example

```sql
INSERT INTO factories VALUES
    (1, 10.0, 10.0),
    (2, 130.0, 47.0);
```

____

## Inserting values for specific columns

### Syntax

```sql
INSERT INTO <table_name>(<column_1_name>, <column_2_name>, ..., <column_n_name>) VALUES (<column_1_value>, <column_2_value>, ..., <column_n_value>);
```

### Example

```sql
INSERT INTO cars(model_id, factory_id) VALUES (1, 2);
```

____