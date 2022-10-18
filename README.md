# SQL_learn
## some examples of SQL

### для выборки с условиями

```
SELECT id, sum FROM orders WHERE products_count > 3

SELECT * FROM orders WHERE status != "cancelled"
# вместо != можно и такие варианты: <>, NOT LIKE, NOT IN ("cancelled")
```
