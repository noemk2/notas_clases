##DML
DML trata del contenido de la base de datos. Son las siglas de Data Manipulation Language y sus comandos son:
A difenrencia de DDL (tiene con formar la estructura de base de datos) se utiliza muy al inicio del proyecto
DML por el contrario trata no de la estructura de la base de datos, sino del contenido de la base de datos, se trata mas bien de meter, actualizar borrar, traer datos de las tablas que ya generamos previamente con el lenguaje ddl
DML = Data Manipulation Language

- Insert: Inserta o agrega nuevos registros a la tabla.
- Update: Actualiza o modifica los datos que ya existen.
- Delete: Esta sentencia es riesgosa porque puede borrar el contenido de una tabla.
- Select: Trae información de la base de datos.

##Insert
Agrega un nuevo registro o tupla a nuestra base de datos
Es importante mantener el orden al momento de declarar

```sql
INSER INTO people (last_name, first_name, adress, city)

VALUES ('Hernandez', 'Laura', 'Calle 21', 'Monterrey');
```

se inserta un registro nuevo en nuestra base de datos (se inserta una fila)

##Update
update no va inserta datos, sino existen ya en nuestra tabla

```sql
UPDATE people
SET last_name = 'Chavez', city = 'Merida'
WHERE person_id = 1;

UPDATE people
SET last_name = 'Juan'
WHERE city = 'Merida';

UPDATE people
SET first_name = 'Juan';
```

##Delete

```sql
DELETE FROM people
WHERE person_id = 1;

DELETE FROM people;
```

```sql
DELETE FROM people
WHERE person_id =1;
```

##Select
trae información de la base de datos muchas veces para generar una vista o
tiene 2 partes :

- Select que dice que campos quieres ver
- FROM que dice de donde vas obtener esos campos
- WHERE permite ver los registro que nos interesa

```sql
SELECT first_name, last_name
FROM people;
```
