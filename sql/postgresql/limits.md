https://metanit.com/sql/postgresql/2.4.php

### PRIMARY KEY

```sql
CREATE TABLE sample(
    field_name VARCHAR(150) PRIMARY KEY
);
```

или

```sql
CREATE TABLE sample(
    field_name VARCHAR(150),
    ...,
    PRIMARY KEY(field_name)
);
```

Первичный ключ уникально идентифицирует поле в таблице. Первичные ключи могут представлять любой тип в таблице.

Первичный ключ может быть составным (compound key):

```sql
CREATE TABLE sample(
    field_name VARCHAR(150),
    field_name2 VARCHAR(150),
    ...,
    PRIMARY KEY(field_name, field_name2) -- поля field_name и field_name2 выступают как составной первичный ключ. В таблице sample не может быть строки, где для обоих полей будет указано одинаковое значение
);
```

---

### UNIQUE

```sql
CREATE TABLE sample(
    field_name VARCHAR(150) UNIQUE
);
```

или

```sql
CREATE TABLE sample(
    field_name VARCHAR(150),
    ...,
    UNIQUE(field_name)
);
```

или

```sql
CREATE TABLE sample(
    field_name VARCHAR(150),
    field_name2 VARCHAR(150),
    ...,
    UNIQUE(field_name, field_name2)
);
```

Поля помеченные как `UNIQUE` имеют только уникальные значения.

---

### NULL и NOT NULL

Указывают на то, может ли поле принимать NULL значение. По умолчанию поле допускает использование NULL.

```sql
CREATE TABLE sample(
    field_name VARCHAR(150) NOT NULL, -- не допускает использования NULL
    field_name2 VARCHAR(150) NULL, -- допускает использование NULL
    field_name3 VARCHAR(150), -- допускает использование NULL
);
```

---

### DEFAULT

Определяет значение по умолчанию для поля, если при добавлении данных они не были указаны.

```sql
CREATE TABLE sample(
    field_name INTEGER DEFAULT 2148
);
```

---

### CHECK

Ограничитель задает ограничение для диапазона значений, которые могут хранится в поле. Условие ограничения указываются в скобках после ограничителя.

```sql
CREATE TABLE sample(
    field_name INTEGER CHECK(field_name > 23 AND field_name < 45),
    field_name2 VARCHAR(150) CHECK(field_name2 != 'hello')
);
```

или

```sql
CREATE TABLE sample(
    field_name INTEGER,
    field_name2 VARCHAR(150),
    CHECK((field_name > 23 AND field_name < 45) AND (field_name2 != 'hello'))
);
```

---

### Оператор CONSTRAINT

Оператор задаёт имена для ограничений (PRIMARY KEY, UNIQUE, CHECK)

```sql
CREATE TABLE sample(
    field_name INTEGER CONSTRAINT lt_name1 PRIMARY KEY,
    field_name2 VARCHAR(150) CONSTRAINT lt_name2 UNIQUE,
);
```

или

```sql
CREATE TABLE sample(
    field_name INTEGER CONSTRAINT lt_name1 PRIMARY KEY,
    field_name2 VARCHAR(150),
    CONSTRAINT lt_name1 PRIMARY KEY(field_name),
    CONSTRAINT lt_name2 UNIQUE(field_name2)
);
```

---

#### Разница между PRIMARY KEY и UNIQUE

- В таблице может быть только один индекс, объявленный как `PRIMARY KEY` и несколько `UNIQUE` индексов.
- Поля, которые входят в состав индекса `PRIMARY KEY` автоматически определяются как `NOT NULL`. В поле с ограничителем `UNIQUE` может быть только 1 `NULL` поле
