### ALTER TABLE

`ALTER TABLE` - добавление, удаление, модифицирование столбцов в существующей таблице; добавление и удаление различных ограничителей.

---

1. ADD

```sql
ALTER TABLE employee ADD salary smallint; -- добавить в таблицу employee поле salary
```

> Все строки будут иметь значение по умолчанию в новом созданном столбце, которое, в данном случае, является NULL

---

2. DROP COLUMN

```sql
ALTER TABLE employee DROP COLUMN first_name; -- удалить из таблицы employee поле first_name
```

> Столбец, вместе со всеми его данными, будет полностью удалён из таблицы.

---

3. RENAME

```sql
ALTER TABLE employee RENAME gender TO SEX; -- переименовать в таблице employee поле gender
```
