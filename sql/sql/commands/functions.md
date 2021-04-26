### Functions

```sql

--- Math ---

SELECT first_name, SQRT(salary) FROM employee LIMIT 7; -- ф-я SQRT() возвращает квадратный корень заданного значения в аргументе
SELECT AVG(salary) FROM employee; -- ф-я AVG() возвращает среднее значение числового столбца
SELECT SUM(salary) FROM employee; -- ф-я SUM() возвращает сумму всех значений столбца
SELECT MIN(salary) FROM employee; -- ф-я MIN() возвращает минимальное из всех значений столбца


--- Strings ---

SELECT COALESCE(email, 'not applicable') FROM employee OFFSET 354 LIMIT 7; -- COALESCE заменяет null-значения в колонке email на 'not applicable'
SELECT CONCAT(first_name, ' - ', gender) [AS new_column] FROM employee LIMIT 7; -- Конкатенация нескольких текстовых значений и возврат полученной строки | с помощью AS возвращаемую строку можно сделать как новую колонку
SELECT first_name, UPPER(last_name) FROM employee LIMIT 7; -- ф-я UPPER() конвертирует все буквы в указанной строке в верхний регистр
SELECT first_name, LOWER(last_name) FROM employee LIMIT 7; -- ф-я LOWER() конвертирует все буквы в указанной строке в нижний регистр
```