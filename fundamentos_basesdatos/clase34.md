GROUP BY

se utiliza bastante en base de datos
GROUP BY tiene que ver con agrupación.
lo que va decir es indicarle a la base de datos que criterios le vas dar para agrupar la tabla
Indica a la base de datos qué criterios debe tener en cuenta para agrupar
agugar la tabla ya la hemos visto 1 sola vez en la clase SELECT; agrupo toda la tabla junta y le aplico una funcion de conteo
ESTE select lo que hizo es contar los registros que teniamos en esa tabla
GROUP BY es mucho mas poderoso que select
cuando le empiezas a meter algunos parametros adicionales
que te ayuda agrupar de manera funcional los datos

```sql
SELECT estatus, COUNT(\*) post_quantily
FROM posts
(si hacemos esto deberia traernos todos posts agrupados juntos, pero queremos agruparlos de alguna manera)
GROUP BY estatus
```

esto nos data 2 colunas (estatus y post_quantily) (binarias) y 2 rows, activo y inactivos
este es el poder de group
la agrupacion nos permite saber cuanto hay en lugar, si manejas valores numericos

```sql
SELECT estatus, SUM(id) suma_id (sumar el id)
FROM posts
GROUP BY estatus
```

esto resulta util (suma) cifras de una cuenta bancaria que tienes sumar, vamos a selectionar de cuenta bancria lo que se ha gastado en entretenimiento, e insumo
tiene mucho que ver con informes que se presentan, tiene ver (no tiene que ver con datos en bruto)solo dime cuantos post se escribieron en este mes, dime cuantos usurios escribieron en este mes

```sql
SELECT YEAR(fecha_publicacion) AS post_year, COUNT() AS post_quantily  (year lo que nos trae solamente la seccion ano (podemos colocar fecha completa)  )
FROM posts
*GROUP BY estatus
*GROUP BY post_year
(esta vez ya no lo vamos agupar por estatus)
(lo vamos a agurpar por post_year)
Vamos a tomar tomar los post y los vamos agrupar por ano
```

vamos a mostrar cuantos post se hicieron en ese ano
vamos a mostrar cuantos post se hicieron en ese mes

```sql
SELECT estatus, MONTHNAME(fecha_publicacion) AS post_month, COUNT() AS post_quantily  (year lo que nos trae solamente la seccion ano (podemos colocar fecha completa)  )
FROM posts
GROUP BY post_month
```

Aqui nos muestra los activos en cada mes y los inactivos en cada mes
podemos agrupar por multiples criterios
para agupar por varios criterios los separas por comas
si quieres agrupar gastos y decir cuanto gastamos en este mes, en esta categoria y luego sumarlo
