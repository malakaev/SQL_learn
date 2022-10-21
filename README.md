# SQL_learn
## some examples of SQL

### для выборки с условиями

```
SELECT id, sum FROM orders WHERE products_count > 3;

SELECT * FROM orders WHERE status != "cancelled";
-- вместо != можно и такие варианты: <>, NOT LIKE, NOT IN ("cancelled")

SELECT id, `sum` FROM orders WHERE products_count > 3 AND id IS NOT null ORDER BY id --;

SELECT * FROM orders WHERE `status` IN ('cancelled', 'returned')

SELECT * FROM orders WHERE `status` = 'cancelled' AND `sum` BETWEEN 3000 AND 10000
SELECT * FROM orders WHERE `status` = 'cancelled' AND `sum` NOT BETWEEN 3000 AND 10000
```

### сортировка
```
SELECT * FROM products ORDER BY price DESC, count; 
-- отсортирует по столбцу price по убыванию, а затем по count (ASC по возрастанию, DESC по убыванию).

SELECT * FROM products ORDER BY price LIMIT 10, 5; 
-- LIMIT 5 выведет первые 5 строк, LIMIT 10, 5 выведет 5 строк начиная с 11 т.е. 10 строк пропустит
```
# Создание таблицы
## PostgreSQL 10
```
create table t (
  id integer primary key generated always as identity
);
```
## MySQL
```
CREATE TABLE book (
    book_id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(50),
    author VARCHAR(30),
    price DECIMAL(8, 2),
    amount INT
);
```

# Добавление данных в таблицу
```
INSERT INTO book (title, author, price, amount)
VALUES ('Мастер и Маргарита', 'Булгаков М.А.', 670.99, 3);
-- Если не указать какое-то поле, оно будет заполнено значением NULL

-- Добавление нескольких строк
INSERT INTO book (title, author, price, amount)
VALUES ('Белая гвардия', 'Булгаков М.А.', 540.5, 5);
INSERT INTO book (title, author, price, amount)
VALUES ('Идиот', 'Достоевский Ф.М.', 460, 10);
INSERT INTO book (title, author, price, amount)
VALUES ('Братья Карамазовы', 'Достоевский Ф.М.', 799.01, 2);
```

