## clase27 ¿Por qué las consultas son tan importantes?

Las consultas o queries a una base de datos son una parte fundamental
ya que esto podría salvar un negocio o empresa.
Alrededor de las consultas a las bases de datos se han creado varias especialidades como ETL o
transformación de datos, business intelligence e incluso machine learning.

las consultas pueden salvar negocio o empresa
las empresas tienen una gran nesecidad por información correcta, exacta, oportuna
en las bases de datos muchas veces tenemos; clientes, productos, proveedores y diferentes tipos de entidades
estos por separado no tiene mucho sentido, pero cuando las empiezas a unir atraves de querys puedes presentar un informe, una tendencia de tal forma que las personas que esan a cargo maniobrar la empresa de un lado o para otro, tengan la informacion que neseciten para tomar las decisiones correctas
Alrededor de toda esta cultura de extraer informacion, se han creado varias especialidades en el esquema de datos, que tienen que ver por ejemplo:

- ETL (transformación de datos)
- business intelligence (extracion y utilizacion de datos para el negocio, para tomar decisiones correctas, incluso machine learning)

## clase28 Estructura básica de un Query

Aprendiendo hacer querys
las estructura de un query puede ser simple o compleja
Los queries son la forma en la que estructuramos las preguntas que se harán a la base de datos.
tener la habilidad de convertir una pregunta en un query de base de datos
Transforma preguntas en sintaxis.

El query tiene básicamente 2 partes:
SELECT y FROM y puede aparecer una tercera como WHERE.
La estrellita o asterisco (\*) quiere decir que vamos a seleccionar todo sin filtrar campos.

Estructura basica de un Query:

```sql
SELECT city, count(\*) AS total
FROM people
WHERE active = true (condicion where; solo traeme cuando active = true)
GROUP BY city (group by ; nos permite agrupar por criterio, en este caso city)
ORDER BY total DESC  (ORDER BY; ya que tenemos estas personas (por ciudad) ordena por el total, con la cantidad mayor de personas de primero haci hacia abajo hasta la que tiene menos personas)
HAVING total >= 2; (HAVING va filtrar cuando el total sea major o igual a 2 )
```

la forma mas sensilla de un query

```sql
SELECT * (selecciona todo, no queremos filtrar campos)
FROM posts (de donde queremos que tome los datos)
resumen: este query trae todo la tabla posts y mostrar todos los campos
---
normalmente se encuentra con where
WHERE fecha_publicacion > '2024' (filtra cuales de estos datos vamos a querer)
```

## clase29 SELECT

esta es la primera parte de la estructura que necitamos tener para hacer preguntas a las bases de datos para hacer querys
SELECT se encarga de proyectar o mostrar datos.
aun no emos echo agregar datos de prueba
El nombre de las columnas o campos que estamos consultando puede ser cambiado utilizando AS después del nombre del campo y poniendo el nuevo que queremos tener:
AS es como
COUNT es contar
la sentencia SELECT de lo que se encarga es de proyectar (proyectar es mostrar), se va encargar de presentar los datos, se encargara de decir que campos se mostraran en el query al final

```sql
SELECT * (es el mas basico) (select no funciona por si mismo)
FROM posts;
```

```sql
SELECT titulo,fecha_publicacion,estutus
FROM posts;
```

select se encarga de filtrar que campos trae (proyectar) de todos los que tenemos en nuestra tabla

##alias
nos permite referinos con otro nombre

AS (como) propiedad para cambiar que se le da el resultado

```sql
SELECT titulo AS encabezado
FROM posts;
```

cuando nosotros tenemos una funcion de agrupacion (mas adelante con group by)
Existe una función de SELECT para poder contar la cantidad de registros.
Esa información (un número) será el resultado del query:
Existe una función de SELECT para poder contar la cantidad de registros.
Lo que nos puede hacer select es permitirnos hacer datos que se crean al momento y que nos pueden agregar información
Una de las formas que podemos hacer esto:

- COUNT(/\*) (count lo que va ser es contar los registros de la tabla)

Lo que hacemos generalmente es agrupar por diferentes criterios y categorias (usuarios)
Pero el count mas sensillo es count(\*)

```sql
SELECT COUNT(/*)
FROM posts;
```

Ahora select no va a traer todos los registros, ya no va traer varias columnas, ni tuplas
Simplemente va traer un numero que es el conteo total de los post que tenemos en nuestra tabla
Muchas veces count(\*) no dice mucho si lo conectas a una aplicacion, luego traer ese dato es complicado, porque count(\*) tiene una sintaxis rara
Lo que podemos hacer en este caso es colocar un alias

```sql
SELECT COUNT(\*) AS numero_posts
FROM posts;
```

Ahora la columan se llamara numero posts, AHORA esto tiene mucho mas sentido
Antes Nos retornaba un columna que se llama COUNT(\*)
De esta manera empezamos a jugar con esta idea de que select nos va permitir traer diferentes clases de información, filtrar las columnas que queremos traer, renombrar las columnas y datos
Tambien hacer datos "on the fly" datos que se crean al momento
No existe guardado en ningun lado
Lo que esta haciendo es ir tupla por tupla en la tabla y contar cuantas tenemos
y que muestre un numero final
el dato (lo que arroga count) no esta almacenado en la base de datos
sin embargo lo podemos consultar, gracias a la magia de select
La sentencia select nos ayuda a proyectar o mostrar los valores y los campos que queremos enseñar al final de nuestro query

## clase30 FROM

Anteriormente era: Seleciona todo y traelo de tal tabla
sin embargo la parte interesante es cuando queremos unir tablas
en normalizacion vemos como las tablas las empezamos a separar
PERO a la hora de presentar un informe, traer información que sea valiosa nosotros requerimos de volver a juntar esa información
continuamos viendo la estructura de un querys y preguntar cosas interesantes a la base de datos
from es una de mas poderosas e interesantes que vamos a utilizar a la hora de hacer un query
from indica de donde vamos a tener que traer los datos
FROM indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es JOIN.

COMO parte de esta sentecia FROM tenemo un compañero inseparable Que es la sentecia JOIN

Existen diferentes tipos de join:

- diferencia : LEFT JOIN, RIGHT JOIN

- diferencia : LEFT JOIN:
- en el LEFT JOIN normal; va traer todos los datos de la tabla A esten o no en la tabla B, ejm: si yo tengo un usuario tenga o no tenga post, los voy a unir pero siempre me va traer los usuarios completos tenga o no tenga posts asociados
- en el LEFT JOIN otra Forma: traeme los usuarios pero solo los que no tengan posts asociados

- diferencia : LEFT JOIN:
- en el RIGHT JOIN normal; Traeme todo lo que esta en la tabla B sin importar si esta en la tabla A, ejm: traeme todos los post aunque no tenga ningun usuario que los alla creado (no deberiamos permitir)
- en el RIGHT JOIN que no incluye al intersección; Traeme todos los post en ejm que manejamos, que no tenga ningun usuario asociado SOLO los que no tenga ningun usuario asociado (este es el join que tiene que ver con diferencia)

## Otro tipo de join

intersección es la parte donde se encuentra los 2 diagramas

-intersección: INNER JOIN (join interno) porque va traer los valores que existen tanto en A como en B (va traer los usuarios que tenga post y los post que tenga un usuario asociado, si hay un post que este huerfano o un usuario que no alla creado un post, esos datos no nos va traer)

## Otro tipo de join

##new version
la union y diferencia simetrica parecen muy iguales, pero en la realidad son bastantes diferentes

- union; lo que hace es traer todo (va traer todos los usuarios sin importar que tenga o no post y va traer post sin importar que tenga o no usuarios)
- diferencia simetrica: lo que hace (lo contrario) va traer solamente aquellos usuarios que no tenga ningun post que no ayan escrito nada y va traer los post que esten huerfanos y que no tenga un autor definido (simplemente los dos que no tienen relacion)(los post huerfanos y los post que no nos aya ayudado a escribir ningun post)

JOIN nos ayuda a unir tablas a traves de las relaciones que nosotros creamos
ejm:

- unir la llave primaria de una tabla con la llave foranea que referencia a esa llave primaria de la otra tabla

#clase31
Utilizando la sentecia FROM

primeros diagramas que vimos: LEFT JOIN y RIGHT JOIN
que tiene que ver con traer lo que hay en un lado sin importar lo que hay del otro o lo que tiene solo de un lado que explicitamente no exista en el otro lado

```sql
SELECT *
FROM usuarios;
```

nos trae toda la tabla usuarios

- Ahora los usuarios vamos a unirlos con los posts

```sql
SELECT *
FROM usuarios
	LEFT JOIN posts ON usuarios.id = posts.usuario_id ;(va tomar la tabla que ya tiene (usuarios)(que esta a la izquierda(la primera que pusimos))y lo vamos unir con la tabla posts, Y la tabla posts asi nomas, se une gracias a una llave foranea que nos va permitir saber el posts quien lo escribio y esto lo vamos hacer atraves de la sentecia ON)
```

lo que hace el LEFT JOIN es tengo todos los usuarios (A) sin importar que tengan o no tengan posts(B)

#Ahora vamos con lo opuesto a LEFT JOIN normal
Ahora vamos a sacar los usuarios que si tienen post asociados

```sql
SELECT *
FROM usuarios
	LEFT JOIN posts ON usuarios.id = posts.usuario_id ;(va tomar la tabla que ya tiene (usuarios)(que esta a la izquierda(la primera que pusimos))y lo vamos unir con la tabla posts, Y la tabla posts asi nomas, se une gracias a una llave foranea que nos va permitir saber el posts quien lo escribio y esto lo vamos hacer atraves de la sentecia ON)
WHERE posts.usuario_id IS NULL;
```

- trae solo el usuario perezoso

#Usando RIGHT JOIN

```sql
SELECT *
FROM usuarios
	RIGHT posts ON usuarios.id = posts.usuario_id ; (primero nos va traer los posts, sin importar que si tienen asociado o no un usuario (A) y del otro lado va traer solo los usuarios que esten asociados a un post (B))
```

Nos trae todos menos el usuario perezoso
Pero nos trae un post huerfano que no tiene asociado a ningun usuario

- el RIGHT JOIN primero nos trae los posts sin importarme otra condicion y despues ya veo cuales son los usuarios que se asocian a cada post
  (aunque no haya posts que no tengan ningun usuario)

#Usando lo contrario a RIGHT JOIN

```sql
SELECT *
FROM usuarios
	RIGHT JOIN posts ON usuarios.id = posts.usuario_id
WHERE posts.usuario_id IS NULL;
```

- solo nos trae nuestro post huerfano
- nos trae todos los datos del post pero del lado de los datos del usuario quien los creo todo viene null

# Segunda Parte: Interseccion, Union, Diferencia Simetrica

La intersección tiene que ver con lo que vimos inicialmente
