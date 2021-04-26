### UPDATE

> Выражение ```UPDATE``` позволяет изменить данные в таблице.

```sql

UPDATE employee
SET salary = 3000, first_name = "david"
WHERE id = 56; -- обновить поля salary и first_name в строке таблицы employee с id 56

```

> Если блок ```WHERE``` не указан, то обновлятся будут *_все записи в таблице_*