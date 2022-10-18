# SQL_learn
## some examples of SQL

### для выборки с условиями

```
SELECT id, sum FROM orders WHERE products_count > 3;

SELECT * FROM orders WHERE status != "cancelled";
# вместо != можно и такие варианты: <>, NOT LIKE, NOT IN ("cancelled")

SELECT id, `sum` FROM orders WHERE products_count > 3 AND id IS NOT null ORDER BY id --;

SELECT * FROM orders WHERE `status` IN ('cancelled', 'returned')

SELECT * FROM orders WHERE `status` = 'cancelled' AND `sum` BETWEEN 3000 AND 10000
SELECT * FROM orders WHERE `status` = 'cancelled' AND `sum` NOT BETWEEN 3000 AND 10000
```
