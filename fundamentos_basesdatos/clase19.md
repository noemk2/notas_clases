##DDL create
SQL tiene dos grandes sublenguajes:
DDL o Data Definition Language que nos ayuda a crear la estructura de una base de datos.

Existen 3 grandes comandos DDL:

Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.
Alter: Ayuda a alterar o modificar entidades.
Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.

3 objetos que manipularemos con el lenguaje DDL:

- Database o bases de datos (squemas)
- Table o tablas. Son la traducción a SQL de las entidades. Las tablas son la proyección en sql de las entidades que estabamos viendo(Entidades)
- View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible. Cuando normalizamos la informacion se ha repartido en padazos y para hacerlo mas coherente y que sirva como informacion. Muchas veces utilizamos el SELECT y esto lo podemos almacenar en una vista de manera coherente

Primeras sentencias

#Create Database o crear una base de datos

```sql
CREATE DATABASE test_db;
USE DATABASE test_db; (quieres usar esta base de datos por default)
```

```sql
USE DATABASE test_db; (seleccionamos una base de datos)
```

Crear una tabla o entiddad(Create table)
##modelo

```sql
CREATE TABLE  people(
	person_id int,
	last_name varchar(255),
	first_name varchar(255),
	address varchar(255),
	city varchar(255)
)
```

##Comando para crear una tabla o entidad con sus constrains

```sql
CREATE TABLE  'platziblog'.'people' (
	'person_id' INT NOT NULL AUTO_INCREMENT,
	'last_name' VARCHAR(255) NULL,
	'first_name' VARCHAR(255) NULL,
	'address' VARCHAR(255) NULL,
	'city' VARCHAR(255) NULL,
	PRIMARY KEY ('person_id'));
```

person_id, etc son columnas
