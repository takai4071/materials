### UNION

```UNION``` - комбинирует несколько наборов данных в один набор и убирает любые существующие дубликаты.

Оператор ```UNION``` используется вместе с ```SELECT```.

Все выражения ```SELECT``` внутри ```UNION``` должны иметь _одинаковое количество стобцов_. Столбцы также должны иметь _одинаковые типы данных_.

---
```UNION ALL``` - комбинирует несколько наборов данных в один набор, не убирает дубликаты

> ```UNION ALL``` работает быстрее, чем ```UNION```, потому что он не выполняет операцию удаления дубликатов в наборе данных
---
```sql
SELECT first_name from employees
UNION
SELECT first_name from customers; -- выбрать все значения поля first_name из employees и customers без повторений

SELECT first_name from employees
UNION ALL
SELECT first_name from customers; -- выбрать все поля first_name из employees и customers
```