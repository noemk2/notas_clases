##DML
a diferencia de ddl tiene que ver en formar la estructura de la base de datos, nuestras tablas, entidad relaciones, los constrains y se utiliza muy al inicio del proyecto y rara vez se utiliza a lo largo del mismo
dml por el contrario no trata sobre la estructura de base de datos SINO del contenido de la base de datos
Se trata mas bien de meter, actualizar, borar, extraer datos de las tablas que ya generamos previamente con el lenguage ddl
DML trata del contenido de la base de datos.
Son las siglas de Data Manipulation Language y sus comandos son:

Insert: Inserta o agrega nuevos registros a la tabla.
Update: Actualiza o modifica los datos que ya existen.
Delete: Esta sentencia es riesgosa porque puede borrar el contenido de una tabla.
Select: Trae información de la base de datos.

##Insert
por lo general lo insterta en la ultima fila
una tupla es un registro y tambien es renglon
como su nombre indica, inserta, agrega un nuevo registro o tupla a nuestra tabla en la base de dato
ejemplo: tenemos una hoja de calculo, lo que vamos hacer es insertar registros o renglones por cada sentencia insert que hagamos

```sql
INSERT INTO people (last_name, first_name, address, city) (puedes insertar todos los campos o puedes insertar campos vacios (entra le valor por defecto que es none, pero podemos definir un constrains valor por defecto))
VALUES ('Hernandez', 'Laura', 'Calle 21', 'Monterrey'); (values son cada uno de los valores de los campos que mencionamos arriva, es muy importante mantener el orden)
```

para saber que se agrego el renglon

```sql
SELECT *FROM platzi_test.people;
```

##update
tiene que ver con actualizar o modificar los datos que ya tenemos
update no va insertar los datos, si no existen ya en nuestra tabla, sino que va tomar un dato que nosotros le indiquemos y el renglon lo va a cambiar
existen diferentest tipos de cambios

1. Primero

```sql
UPDATE people (el update a la tabla people)
SET last_name = 'Chavez', city = 'Merida' (set es lo nos indica qu campo va tener que valor, actualiza la tabla people y cambia el campo last_name por el valor chavez y cambia city por Merida )
(aqui estoy diciendo a que campo quiero que cambies pero no estoy diciendo a que persona quiero que actualize la informacion, no estoy diciendo cual es el renglon que quiero cambiar)
WHERE person_id= 1; (WHERE nos indica el renglon que queremos cambiar)
```

```sql
UPDATE people
SET first_name = 'Juan'
WHERE city = 'Merida';
```

Aqui estas haciendo un update inseguro; estas haciendo un update masivo, va modificar un registro que repetira

```sql
Update people
SET first_name = 'Juan';
```

##Delete
puede ser riesgosa porque puede borrar el contenido de una tabla y es simil con lo anterior (sintaxis)

```sql
DELETE FROM people
WHERE person_id = 1; (aqui borra solo donde person_id =1)

DELETE FROM people; (aqui borra toda la tabla)
```

##Select
select trae informacion de base de datos
muchas veces para generar una vista
primero necesitamos extraer la informacion y luego ponerla en otro lado
tambien se le agrega where, que te permite ver los registros que te interesan

```sql
SELECT first_name, last_name
FROM people;
```
