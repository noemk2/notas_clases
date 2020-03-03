#ORDER BY y HAVING
ya tienes todo lo necesario para presentar informacion, para extraerla al frente de manera que haga sentido que ofresca valor
y con este set de herramientas que tienes hasta ahorita, ya vas muy bien armado

estas sentencias sirven en el ambito de la base de datos
ordenar por "te ordene los datos por un criterio"
La sentencia ORDER BY tiene que ver con el ordenamiento de los datos dependiendo de los criterios que quieras usar.

ASC sirve para ordenar de forma ascendente.
DESC sirve para ordenar de forma descendente.
LIMIT se usa para limitar la cantidad de resultados que arroja el query.
HAVING tiene una similitud muy grande con WHERE, sin embargo el uso de ellos depende del orden.
Cuando se quiere seleccionar tuplas agrupadas únicamente se puede hacer con HAVING.

```sql
SELECT *
FROM posts
```

por default te muestra en orden que fueron creadas
pero vamos a modificar este orden para dar mas sentido a los datos que tenemos

```sql
SELECT *
FROM posts
ORDER BY fecha_publicacion
(hay 2 formas de ordenar: de manera ascendente y descendente, por default nos ordena de manera ascendente)
```

```sql
SELECT *
FROM posts
ORDER BY fecha_publicacion DESC;
```

Ordenar por cadena
esto nos puede ayudar cuando tienes un titulo (que es un string) lo va ordenar por orden alfabetico
en orden ascendente comienza con el valor minimo (puede ser nulo)

#hay un complemento al ORDER BY , es otra sentencia paro siempre va en conjunto

```sql
SELECT *
FROM posts
ORDER BY fecha_publicacion ASC;
LIMIT 5
quiero traerme los 5 primeros
```

## HAVING no es muy utilizada pero es necesario que la sepas. porque va haber casos muy particulares que te va ser sumamente util

tine una similiaridad con where pero vamos a ver donde radica la diferencia y porque es importante que sepas having

creando un select mas complejo

```sql
SELECT MONTHNAME(fecha_publicacion) AS post_month estatus, COUNT(\*) AS post_quality
FROM posts
GROUP BY estatus, post_month
ORDER BY post_month
```

nos arroja cuandtos posts hay en abril en cualquier ano que esten activos o inactivos

AHORA queremos ver solamente los meses en que solo tenemos mas de un posts

```sql
SELECT MONTHNAME(fecha_publicacion) AS post_month estatus, COUNT(\*) AS post_quality
FROM posts
WHERE post_quality > 1
GROUP BY estatus, post_month
ORDER BY post_month
```

esto nos da error, este error tine culpa el orden
where nos ayuda a seleccionar los rows pero los selecciona antes de hacer la parte de agrupacion
la agrupacion nos permitio contar contar esta (COUNT(\*)) basandonos en el mes, estatus y estatus
Hasta que no agrupamos por mes y por estatus
entonces where todabia no conoce el valor de post_quality
Cuando queras hacer una selection de tuplas o de rows la haces con where
PERO una ves que quieres hacer una selection de tuplas y rows AGRUPADOS

```sql
SELECT MONTHNAME(fecha_publicacion) AS post_month estatus, COUNT(\*) AS post_quality
FROM posts
no sirven en agrupaciones WHERE post_quality > 1
GROUP BY estatus, post_month
ORDER BY post_month
HAVING post_quality > 1
```

- Aqui error porque having va despues de group, lo que haces:

1. Agrupar y contar
2. despues filtras y luego
3. ordenar

HAVING y WHERE tienen muchas similitudes y lo que ayudan es a filtrar tambien, tiene una estructura muy similar
HAVING tiene en particular que nos ayuda una vez de agrupamos campos dinamicos que nos cuentan o nos suman valores

```sql
SELECT MONTHNAME(fecha_publicacion) AS post_month estatus, COUNT(\*) AS post_quality
FROM posts
no sirven en agrupaciones WHERE post_quality > 1
GROUP BY estatus, post_month
HAVING post_quality > 1
ORDER BY post_month
```
