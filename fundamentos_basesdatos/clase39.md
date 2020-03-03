Consultando PlatziBlog
Puedes usar una abreviación para evitar escribir lo mismo cada vez.

Ejemplo:

```
FROM categorias AS c
```

vamos hacer un query
Donde traigamos las categorias, pero las vamos a ordenar por las que tienen mas post a menos

```
SELECT c.nombre_categoria, COUNT(\*) AS cant_posts
FROM categorias AS c
	INNER JOIN post AS p ON c.id =p.categoria_id
GROUP BY c.id
ORDER BY cant_posts DESC
```

cual es la categoria que tiene mas post

```
SELECT c.nombre_categoria, COUNT(\*) AS cant_posts
FROM categorias AS c
	INNER JOIN post AS p ON c.id =p.categoria_id
GROUP BY c.id
ORDER BY cant_posts DESC
LIMIT 1
```

que usuario a estado creando mas post en el sistema

```
SELECT u.nickname, COUNT(\*)
FROM usuarios AS u
	INNER JOIN post AS p ON u.id = p.usuario_id
GROUP BY u.id
ORDER BY cant_posts DESC
```

Agregando que categorias esta escribiendo el autor

```
SELECT u.nickname, COUNT(\*) cant_posts GROUP_CONCAT(nombre_categoria)
FROM usuarios AS u
	INNER JOIN post AS p ON u.id = p.usuario_id
	INNER JOIN categorias AS c ON c.id = p.categoria_id
GROUP BY u.id
 RDER BY cant_posts DESC
```

GROUP COUNCAT no regresa en vez de un numero sumado nos regresa los valores separados por coma

Ver que usurios si son escritores de nuestro periodico que no estan haciendo su trabajo

```sql
SELECT *
FROM usuarios AS u
	LEFT JOIN post ON u.id = post.usuarios_id
WHERE post.usuario_id = IS NULL
```
