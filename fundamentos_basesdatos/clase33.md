##Utilizando la sentencia WHERE nulo y no nulo

El valor nulo en una tabla generalmente es su valor por defecto cuando nadie le asignó algo diferente.
el null no es exactamente un tipo de dato (pero se puede considerar un tipo de dato)
estos se pueden considerar como:
La sintaxis para hacer búsquedas de datos nulos es IS NULL.
La sintaxis para buscar datos que no son nulos es IS NOT NULL

exiten campos que si te permiten colocar valores nulos
puede exitir campos que deberia ser NOT NULL pero no lo hicieron de esa manera

## Como consultar a traves de WHERE cuando tenemos un valor nulo hasta ahora vimos operadores de consulta como > =

Para consultar valores de tipo nulo no utilizamos estos
lo vamos a interpretar como un valor vacio

## Aquellos post que no tengan usuario asociado

para que estos no tengan usuario asociado, la condicion tiene que ser que "usuario_id" sea nulo

## Como lo traduciomos a un WHERE

```sql
SELECT *
FROM post
WHERE usuario_id = null (esto es un error, poque nulo es igual a nada)
WHERE usuario_id IS NULL
```

## la mayoria de las veces NO nos interesa traer valores nulos, NOS interesa traer valores que NO SON nulos

```sql
SELECT *
FROM post
WHERE usuario_id IS NOT NULL
(nos traera todos los post menos el post huerfano)
```

## Ahora para ser los where hay un condicion extra que se llama AND

esta condicion nos va unir criterio a nuestra busquedas
por EJEMPLO: en el case anterior estabamos trallendo todos los post que si tienen un usuario asociado, pero ademas quiero filtralo por que este activo

```sql
SELECT *
FROM post
WHERE usuario_id IS NOT NULL
	AND estatus = 'activo'
	AND id < 50
	AND categoria_id = 2
```

nos trae ademas los usuario activos
