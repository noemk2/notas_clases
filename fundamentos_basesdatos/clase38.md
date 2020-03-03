##Preguntándole a la base de datos
GROUP_CONCAT toma el resultado del query y lo pone como campo separado por comas.
para plantearlo

1. que es lo que queremos sacar con el select, ejm(de tabla post vamos a traer el titulo), luego el conteo de los tag
2. que tablas vamos a necesitamos para tener la informacion, necesitamos saber la union entre varias tablas, vamos a tener que unir a las 3 atraves de esta tabla transitiva
   on nos indica que campo de cada lado los une

- Cuantas etiquetas tiene un blogpost, cuantas etiquetas estan ligadas a los blogpost

```sql
SELECT posts.titulo, COUNT(\*) numero_etiquetas
FROM posts
	INNER JOIN posts_etiquetas ON posts.id = posts_etiquetas.post_id (solo nos interesa los que tienen registros en ambos lados) (posts_etiquetas es la tabla transitiva)
	esto nos dara la unio entre post y posts_etiquetas
	INNER JOIN etiquetas ON etiquetas.id = posts_etiqueta_id
	GROUP BY posts.id
```

nos trae el posts, el titulo del post y cuantas etiquetas tiene ese post

CUAL son los post que tienen mas etiquetas

```sql
SELECT posts.titulo, COUNT(\*) num_etiquetas
FROM posts
	INNER JOIN posts_etiquetas ON posts.id = posts_etiquetas.post_id (solo nos interesa los que tienen registros en ambos lados) (posts_etiquetas es la tabla transitiva)
	esto nos dara la unio entre post y posts_etiquetas
	INNER JOIN etiquetas ON etiquetas.id = posts_etiqueta_id
	GROUP BY posts.id
	ORDER BY num_etiquetas DESC (para saber quien tiene mas de 1ro)
```

- Ahorita estabamos viendo el numero de tags hay en cada post
- Pero ahora me interesa cual son esos tagas

```sql
SELECT posts.titulo, GROUP_CONCAT(nombre_etiqueta)
FROM posts
	INNER JOIN posts_etiquetas ON posts.id = posts_etiquetas.post_id (solo nos interesa los que tienen registros en ambos lados) (posts_etiquetas es la tabla transitiva)
	esto nos dara la unio entre post y posts_etiquetas
	INNER JOIN etiquetas ON etiquetas.id = posts_etiqueta_id
	GROUP BY posts.id
```

resulta: 2 columnas (titulo, GROUP_CONCAT(nombre_etiqueta))
de cata titulo cual son las etiquetas que estan asociadas
GROUP_CONCAT lo que hace es tomar el resultado del query y en vez de ponerlo en row tras otro (cuando lo agrupe) lo que va ser es colocarlo en un campo separado por comas

Otro ejemplo: Cuales son las etiquetas que no tinen ningun post

```sql
SELECT *
FROM etiquetas
	(vamos hacer un LEFT JOIN por que necesitamos saber la relacion entre las etiquetas y cuantos post tiene asociados(la tabla que hace eso no es la tabla post) la tabla que tiene la relacion entre las etiquetas y cuantos post tine es la tabla intermedia (posts_etiquetas))
	LEFT JOIN posts_etiquetas ON etiquetas ON etiquetas.id = posts_etiquetas.etiqueta_id
WHERE posts_etiquetas_id IS NULL (nos traera etiquetas que no tinenen asociados ningun post )
```
