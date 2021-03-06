### SELECT

https://postgrespro.ru/docs/postgresql/9.5/sql-select

```sql
SELECT * FROM employee; -- вывести все значения всех строк
SELECT field_name FROM employee; -- вывести значения всех строк из столбца field_name
SELECT count(*) FROM employee; -- кол-во строк
SELECT * from employee ORDER BY field_name (ASC|DESC) -- все поля сортируются по полю field_name; если ASC (по умолчанию), то поля сортируются по возрастанию; если DESC, то поля сортируются по убыванию
SELECT * from employee ORDER BY field_name1, field_name2 -- все поля сортируются сначала по полю field_name1, потом field_name2
SELECT DISTINCT gender FROM employee ORDER BY gender; -- возвразщает результат без повторений
SELECT * FROM employee WHERE fieldname1='val1' [AND|OR fieldname2='val2']; -- выборка с условием
SELECT * FROM employee [OFFSET 10] LIMIT 5; -- лимит со сдвигом
SELECT * FROM employee OFFSET 20 FETCH FIRST 5 ROW ONLY; -- выборка строк со сдвигом
SELECT * FROM employee WHERE gender [NOT ]IN ('Female', 'Male'); -- выборка из указанных значений | если NOT, то выборка всех строк, кроме строк с указанными значениями в полях
SELECT * FROM employee WHERE date_of_birth BETWEEN '2014-01-01' and '2015-01-01'; -- выборка из указанного диапазона значений. в диапазон также входят нижнее и верхнее значения
SELECT * FROM employee WHERE email [i]LIKE '%@google.com'; -- выборка по указанному шаблону (если с i, то регистр игнорируется)
SELECT gender, COUNT(gender) FROM employee GROUP BY gender; -- группировка по gender, подсчёт количества строк на каждое значение gender
SELECT gender, COUNT(gender) FROM employee GROUP BY gender HAVING count(gender) > 120; -- выбрать строки подходящие по условию HAVING
SELECT first_name, last_name AS surname, gender AS sex FROM employee LIMIT 10; -- использование алиасов с помощью конструкции AS. Также с помощью AS можно сокращать имена таблиц аналогичным способом (используется при использовании полных имён полей)

SELECT first_name, salary+500 AS salary FROM employee; -- перезапись старой колонки на новую с помощью арифметического оператора "+" и ключевого слова AS

SELECT first_name, salary FROM employee WHERE salary (SELECT AVG(salary) FROM employee) ORDER BY salary DESC; -- пример подзапроса
```
