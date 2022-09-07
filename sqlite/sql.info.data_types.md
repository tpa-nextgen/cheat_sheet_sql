# Data types

|Type|Description|
|-|-|
|`INTEGER`|stores signed integers|
|`REAL`|stores floating point values|
|`TEXT`|stores text strings using the database encoding|
|`BLOB`|stores blob of data|

Columns can additionaly store `NULL` values regardless of the basic type. To disallow that for a specific column, `NOT NULL` keyword should be used for that column.