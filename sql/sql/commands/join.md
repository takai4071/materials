### JOIN
```sql
SELECT orders.id, customers.name FROM orders INNER JOIN customers ON order.customer_id = customers.id; -- выборка строк из обоих таблиц (по условию после ON)
SELECT orders.id, customers.name FROM orders LEFT JOIN customers ON order.customer_id = customers.id; -- LEFT JOIN - выборка строк из обоих таблиц (по условию после ON) и последующее добавление к результату строк из таблицы перед словом JOIN
SELECT orders.id, customers.name FROM orders RIGHT JOIN customers ON order.customer_id = customers.id; -- RIGHT JOIN - выборка строк из обоих таблиц (по условию после ON) и последующее добавление к результату строк из таблицы после слова JOIN
```