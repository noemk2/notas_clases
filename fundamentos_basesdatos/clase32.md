#WHERE
casi simpre nos encontramos en todos lados: select, from, where
WHERE es la sentencia que nos ayuda a filtrar tuplas o registros dependiendo de las características que elegimos.

La propiedad LIKE nos ayuda a traer registros de los cuales conocemos sólo una parte de la información.
La propiedad BETWEEN nos sirve para arrojar registros que estén en el medio de dos. Por ejemplo los registros con id entre 20 y 30.

```sql
SELECT *
FROM pots
(la sentencia were nos permite filtrar y decir cual de estos rows nos van ha servir en nuestro reporte)
(por ejm: el primero se me ocurre filtrar por el id)
#WHERE id < 50 ; (filtra de 49 para abajo)
WHERE id <= 50 ; (filtra de 49 para abajo)
(esto es filtrando por cuestiones numericas, por eso es importante definir los tipos de datos numericos como numericos y no como cadenas)
(el operador igual funciona muy bien con cadenas, cuando sabes la cadena exacta la cual vas a traer (ejm: estatus: estatus solo puede ser activo o inactivo))
```

```sql
SELECT *
FROM pots
WHERE estatus = 'activo' (linea 7)
WHERE estatus = 'inactivo' (linea 7)
(solo nos traera aquellos que tienen la cadena activo en el estatus)
```

si tienees 2 valores por ejm, o quieres sacar todo lo que nosea un valor
#tambien puedes usar la sentecia no igual

```sql
SELECT *
FROM pots
WHERE estatus != 'activo'
```

ejmplo de uso: cuando quieres buscar los que estan activos

#Propiedad LIKE
cuando no conoces la cadena exacta (en el caso de activo e inactivo, solo havia 2 opciones, era muy facil filtar, pero hay vece que los titulos son muy distintos)
queremos filtar titulos que tengan una características

```sql
SELECT *
FROM pots
WHERE titulo LIKE '%escandalo%' (los porcentajes quiere decir 'traeme una cadena antes de lo que sea despues pero que tenga la palabra escandalo en el medio')
(para que funcione el LIKE la cadena entre comillas)
(donde el titulo sea como, parecido a escandalo)
WHERE titulo LIKE 'escandalo%' (nos traera los row que empiecen con escandalo)
```

## hacer select donde la fecha de publicacion sea mayor al ano 2025 en el mes tal

```sql
SELECT *
FROM pots
WHERE fecha_publicacion > '2025-01-01'
(nos trae fechas que son posteriores a esa fecha)
```

## buscar los que esten entre una fecha a otra

```sql
SELECT *
FROM pots
WHERE fecha_publicacion BETWEEN '2023-01-01' AND '2025-12-31'
(BETWEEN va recivir 2 valores, )
(nos traera todos los posts que ayan sido escrito entre esa fecha)
```

## otra forma de proyectar los datos

en where ademas de traer los datos que ya tenemos en la base de datos, podemos manipularlos un poco

```sql
SELECT *
FROM pots
WHERE YEAR(fecha_publicacion) BETWEEN '2023' AND '2024'
(ahora no me tomes la fecha completa, toma nada mas el ano y quiero que el ano este entre esas fechas)
```

en la fecha de publicacion hasta ahorita solo estamos traendo la fecha completa PERO tambien podemos hacer uso de algo como el ano

```sql
SELECT *
FROM pots
WHERE MONTH(fecha_publicacion) = '04'
(yo quiero saber las noticias que han sido escritas en abril)
(trae todos los anos con fecha de abril, cualquier dia)
```
