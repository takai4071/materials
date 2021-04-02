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
