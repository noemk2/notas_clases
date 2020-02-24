DDL alter
vamos a continuar creando y vamos a crear el ultimo objeto (las vistas)
las vistas estan relacionadas con los select o selecciones
Los Views toman datos de la base de datos,
los hacen presentables y los convierten en algo que podamos consultar de manera recurrente.
vamos a crear estos objeto
Las vistan toman datos de la base de datos ponerlas en una forma presentable y convertirlas en algo que podamos consultar de manera recurrente
este es el comando View

```sql
CREATE VIEW 'v_brasil_customers' AS
	SELECT customer_name, contact_name
	FROM customers
	WHERE country = "Brasil";
```

el comando view tiene 2 partes principales:

1. Asignarle un nombre, se coloca la palabra create, la palabra view que dice que vamos a crear una vista, despues viene el nombre que le quieres asignar a esa vista, ejemplo: v_brasil_customers (por convencion se le coloca v de primero para saber que no es una tabla)
   el select asignar partes de la base de datos y se le asigna a la vista
   otro ejemplo

```sql
USE 'platziblog'; (usa la base de datos 'platziblog')
CREATE OR REPLACE VIEW 'platzi_people' AS (crear o remplazar vista 'platzi_people')
SELECT * FROM platziblog.people; (selecciona las tablas de platziblog)
```

```sql
SELECT * FROM platziblog.platzi_people;
```

la funcion es generar una vista que tenga exactamente los datos que nesecitamos, para presentarlo en un sistema, dar la informacion ya dijerida y presentarlo al usuario
la ventaja esque estas vistas se mantiene en memoria de tal forma que podemos tener esta vista al dia sin necesidad de hacer las consultas cada vez

##Comando de ALter Table
Es el comando que nos permitira modificar

```sql
ALTER TABLE people (ALTER TABLE nos permite modificar nuestra tabla)
ADD date_of_birth_date; (como modificamos la tabla, vamos agregar una columna)

ALTER TABLE people
ALTER COLUMN date_of_birth year (cambiamos el date_of_birth por year);

ALTER TABLE people
ALTER COLUMN date_of_birth;
```

las columas son atributos

```sql
ALTER TABLE 'platziblog'.'people'
AD COLUMN 'date_of_birth' DATETIME NULL AFTER 'city'; (añadir la columna date_of_birth despues de city)
```

###cambiando el tipo de dato de una columna

```sql
ALTER TABLE 'platziblog'.'people'
CHANGE COLUMN 'date_of_birth' 'date_of_birth' VARCHAR(30) NULL DEFAULT NULL;
```

###Borrar una columna

```sql
ALTER TABLE people
DROP COLUMN date_of_birth;
```

```sql
ALTER TABLE 'platziblog'.'people'
DROP COLUMN 'date_of_birth';
```
