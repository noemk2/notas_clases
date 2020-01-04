##¿Qué tan standard es SQL?
La utilidad más grande de SQL fue unificar la forma en la que pensamos y hacemos preguntas a un repositorio de datos. Ahora que nacen nuevas bases de datos igualmente siguen tomando elementos de SQL.
crear la tabla people

```sql
CREATE TABLE people(
	person_id int,
	last_name varchar(255),
	first_name varchar(255),
	address varchar(255),
	city varchar(255)
)
```

insertar un registro

```sql
INSERT INTO people(last_name, first_name, address, city)
VALUES('Hernandez','Laura', 'Calle 21', 'Monterrey');

SELECT first_name, last_name
FROM people;

DROP TABLE people;
```
