mockaroo.com - сайт для генерирования данных

### CREATE

```sql
CREATE DATABASE db_name; -- создать БД с именем db_name
CREATE TABLE employee (
id BIGSERIAL NOT NULL PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
gender VARCHAR(50) NOT NULL,
email VARCHAR(150),
date_of_birth DATE NOT NULL
); -- создать базу employee с указаными полями
```

### INSERT

```sql
INSERT INTO employee(first_name, last_name, gender, email, date_of_birth) VALUES ('John', 'Doe', 'Male', 'jd@mail.com', '2000-01-01'); -- внести в указанные поля базы employee указанные значения
```

### DROP

```sql
DROP DATABASE db_name; - удалить БД с именем db_name
DROP TABLE table_name; - удалить таблицу с именем table_name
```

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
SELECT * FROM employee WHERE gender in ('Female', 'Male'); -- выборка из указанных значений
SELECT * FROM employee WHERE date_of_birth BETWEEN '2014-01-01' and '2015-01-01'; -- выборка из указанного диапазона значений
SELECT * FROM employee WHERE email [i]LIKE '%@google.com'; -- выборка по указанному шаблону (если с i, то регистр игнорируется)
SELECT gender, count(gender) FROM employee GROUP BY gender; -- группировка по gender, подсчёт количества строк на каждое значение gender
SELECT gender, count(gender) FROM employee GROUP BY gender HAVING count(gender) > 120; -- выбрать строки подходящие по условию HAVING
SELECT first_name, last_name AS surname, gender AS sex FROM employee LIMIT 10; -- использование алиасов с помощью конструкции AS
SELECT COALESCE(email, 'not applicable') FROM employee OFFSET 354 LIMIT 7; -- COALESCE заменяет null-значения в колонке email на 'not applicable'
```
