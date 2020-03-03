¿Cómo convertir una pregunta en un query SQL?
De pregunta a Query

SELECT: Lo que quieres mostrar
FROM: De dónde voy a tomar los datos, "ok tengo esto que quiero mostrar, quiero decir, Cuales son las ventas, cual es el equipo que va ganando PERO de done puedo sacar esa informacion, la puedo sacar de 1 tabla, necitos 2 tablas, atraves de que campos voy hacer los joins, para que al final tener un repositorio de datos de donde yo pueda extraer esta informacion"
WHERE: Los filtros de los datos que quieres mostrar ("de toda esta informacion, ya tengo lo quiero mostrar, PERO no quiero toda la informacion, vamos a sacar y solo queremos la informacion relevante")
GROUP BY: Los rubros por los que me interesa agrupar la información ("porque grupos me interesa seleccionar mi información, util para sacar conteos")
ORDER BY: El orden en que quiero presentar mi información (tengo todos los post, los tengo filtrados, pero me intersa saver el que escribio prtimero, te puede servir si quieres sacar los tops de algo, junto con LIMIT)
HAVING: Los filtros que quiero que mis datos agrupados tengan (cuando quieres filtrar nuevamente pero cuando tienes un group by, cuando vas filtar datos que ya sumaste, contaste, en algun grupo, having nos ayuda a referenciar esos campos y filtrarlokj0)

esto no siempre es una transformacion directa
