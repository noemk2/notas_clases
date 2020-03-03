##El interminable agujero de conejo (Nested queries)
Los Nested queries significan que dentro de un query podemos hacer otro query.
Esto sirve para hacer join de tablas, estando una en memoria. También teniendo un query como condicional del otro.

Este proceso puede ser tan profundo como quieras, teniendo infinitos queries anidados.
Se le conoce como un producto cartesiano
ya que se multiplican todos los registros de una tabla con todos los del nuevo query.
Esto provoca que el query sea difícil de procesarpor lo pesado que puede resultar.

te puede servir para hacer una tabla que hagas un join con otra tabla (esta tabla solo existe solo en memoria) pero tambien te sirve para hacer un join en la base de datos
el resultado final de un query lo puedes poner como condition de where
es complejo (su estrutura es un query dentro de otro query)
CUANDO ocupar los nested queries
generalmente los nested queries cuando tienes un problema que no se puede solucionar simplemente consultando tu tabla
que necesitas hacer una agregacion o otro tipo de operacion que viene de otra tabla de tu misma tabla que cuando la agrupas ya no puedes hacer un query de un where que tiene otra condition
necesitas condiciones separadas

1. lo que haces es hacer un query
2. ese query lo conviertes en una tabla o un valor
3. despues eso lo metes como entrada ya sea como from o en el where dentro del segundo query

hay que tener cuidado al utilizar los nested query
existen casos que se les ocurre hacer un nested query en ese momento parece una buena idea, era necesario para el contesto, pero a la larga
cuando los datos comienzan a crecer
y tienen datos de miles o de millones para hacer queries lo que debes hacer es un producto cartesiano
estas haciendo una anidacion que lo que proboca es que el query se haga muy pesado
y que sea difícil de procesar para manejador de base de datos (dependera del servidor y la maquina)
pero en general no escala, se va a una cuestion exponencial
es bueno saber utilizarlos y es no utilizarlos
trata de hacerlo en queries que sabes que no van estar creciendo constantemente en la tabla que se esta utilizando

```sql
SELECT new_table_projection.date, COUNT(\*) AS post_count
(esta vez no vamos agarrar un tabla que viene de nuestra base de datos, sino vamos a crear una tabla dinamica(que esta en momoria) que se va crear al memento de crear ese query)
FROM (
	SELECT DATE(MIN(fecha_publicacion)) AS date, YEAR(fecha_publicacion) AS post_year
	FROM pots
	GROUP BY post_year) AS  new_table_projection
		(esto lo nos va traer es 1 sola, la fecha que va primero)
	GROUP BY new_table_projection
	ORDER BY new_table_projection.date
)
```

```
SELECT *
FROM post
WHERE fecha_publicacion = (
	SELECT MAX(fecha_publicacion)
	FROM post
	)
```

quiero selectionar todo de la tabla post
pero la condicion es que la fecha de pubblicacion sea igual a la fecha de pubblicacion que le vamos a decir a nuestro query
el segundo query solos nos traera (lo vamos a ejecutar por separado)

```
SELECT *
FROM post
WHERE fecha_publicacion = "2030-04-05"
	SELECT MAX(fecha_publicacion)
	FROM post

```
