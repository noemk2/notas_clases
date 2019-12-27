##DDL alter
Los Views toman datos de la base de datos, los hacen presentables y los convierten en algo que podamos consultar de manera recurrente.

### comandos:

```sql
CREATE VIEW v_brasil_customers AS
	SELECT customer_name,
	contact_name
	FROM customers
	WHERE country = "Brasil";
```

```sql
USE 'platziblog';
<!--CREATE VIEW 'platzi_people' AS-->
CREATE OR REPLACE VIEW 'platzi_people' AS
SELECT * FROM platziblog.people;
```

## Alter Table

```sql
ALTER TABLE people
ADD date_of_birth date;

ALTER TABLE  people
ALTER COLUMN date_of_birth year;

ALTER TABLE people
DROP COLUMN date_of_birth;
```

### Cambiando la tabla de city por date_of_birth

```sql
ALTER TABLE 'platziblog'.'people'
ADD COLUMN 'date_of_birth' DATETIME NULL AFTER 'city';
```

### Cambiando el tipo de dato de DATETIME a VARCHAR

```sql
ALTER TABLE 'platziblog'.'people'
CHANGE COLUMN 'date_of_birth' 'date_of_birth' VARCHAR(30) NULL DEFAULT NULL;
```

### Borrar columna "date_of_birth"

```sql
ALTER TABLE 'platziblog'.'people'
DROP COLUMN 'date_of_birth';
```
