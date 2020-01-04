## clase27 ¿Por qué las consultas son tan importantes?

Las consultas o queries a una base de datos son una parte fundamental ya que esto podría salvar un negocio o empresa.
Alrededor de las consultas a las bases de datos se han creado varias especialidades como ETL o transformación de datos, business intelligence e incluso machine learning.

las consultas pueden salvar negocio o empresa

## clase28 Estructura básica de un Query

Los queries son la forma en la que estructuramos las preguntas que se harán a la base de datos. Transforma preguntas en sintaxis.

El query tiene básicamente 2 partes:
SELECT y FROM y puede aparecer una tercera como WHERE.
La estrellita o asterisco (\*) quiere decir que vamos a seleccionar todo sin filtrar campos.

Estructura basica de un Query:

```sql
SELECT city, count(\*) AS total
FROM people
WHERE active = true
GROUP BY city
ORDER BY total DESC
HAVING TOTAL >= 2;
```

## clase29 SELECT

SELECT se encarga de proyectar o mostrar datos.
El nombre de las columnas o campos que estamos consultando puede ser cambiado utilizando AS después del nombre del campo y poniendo el nuevo que queremos tener:
AS es como
COUNT es contar

```sql
SELECT titulo,fecha_publicacion,estutus
FROM posts;
```

```sql
SELECT titulo AS encabezado
FROM posts;
```

Existe una función de SELECT para poder contar la cantidad de registros. Esa información (un número) será el resultado del query:

```sql
SELECT COUNT(/*)
FROM posts;
```

## clase30 FROM

FROM indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es JOIN.

JOIN nos ayuda a unir tablas

Los diagramas de Venn son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia JOIN de la manera adecuada dependiendo del query que se quiere hacer.
FROM indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es JOIN.

Los diagramas de Venn son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia JOIN de la manera adecuada dependiendo del query que se quiere hacer.
los JOINS: nos permiten relacionar unas tablas con otras, para completar la información, esta directamente relaciona con la TEORÍA DE CONJUNTOS

existen varios tipos de JOINS
estan:

LEFT JOIN: es de tipo diferencia, este trae todo el contenido de la tabla principal y algunos datos que este relacionados con la tabla principal Ejemplo:
USURIOS -> POST= trae todos los USUARIOS y los POST que tengan relacion con USUARIOS

RIGHT JOIN: es de tipo diferencia, este trae todo el contenido de la tabla relacionada y algunos datos de la tabla principal que esten relacionados Ejemplo:
USURIOS -> POST= trae todos los POST y los USUARIOS que tengan relación con POST

---

LEFT JOIN:
ON nos dice que campo pertece a cual

```sql
SELECT *
FROM  usuarios
	LEFT JOIN posts ON usuarios_id = posts.usuarios_id;
```

LEFT JOIN down

```sql
SELECT *
FROM  usuarios
	LEFT JOIN posts ON usuarios_id = posts.usuarios_id
WHERE posts.usuarios_id IS NULL;
```

RIGHT JOIN up

```sql
SELECT *
FROM  usuarios
	LEFT JOIN posts ON usuarios_id = posts.usuarios_id;
```
