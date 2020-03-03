Colecciones vs subcolecciones
La particularidad de las top level collections es que existen en el primer nivel de manera intrínseca.
Las subcolecciones ya no vivirán al inicio de la base de datos.

Si tienes una entidad separada que vas a referenciar desde muchos lugares es recomendado usar un top level collection.
Por el otro lado si se necesita hacer algo intrínseco al documento es aconsejable usar subcolecciones.

la estructura es deficil de modificar o imposible en bd relacionales

las bases de datos basados en documentos son mas flexibles al respeto, podemos poner un blogspot que tenga una fecha de publicacion, sin embargo puedo crear otro documento que no la tenga (no es incistente)
ejm
creacion de blogspot, podemos crear un blogspot que tenga titulo, contenido y fecha de publicacion y otro que solo tenga titulo y imagen
puede ser una estructura completamente diferente aunque se este guardando en la mis ma colecion post
VENTAJAS: flexividad
DESVENTAJAS: si yo quisiera consultar los blogspots por fecha de creacion (puede que algunos blogspot, no tenga ese campo, por lo tanto no van a aparecer en tu consulta o querys)

otro tipo de colecion
se puede crear una colecion dentro del documento
este tipo de colecion son totalmente intrínseco al documento (y no al top level)

si vas ocupar los elementos de la colecion de manera independiente, si vas a querer hacer hacer querys separados, listar, varios ducumentos van a tener referencia a esos objetos de esa colecion... vale la pena tenerla como entidad separada
Si encambio tenemos tenemos las etiquetas, que solo le vamos a ver en la entrada de la notica, si solo nos interesa en contexto de nuestro articulo o blogspot, entonces vale la pena guardarla como una subcoleccion de esa noticia en particular... nos interesa listar las etiquetas

si es una entidad separada que vas a referenciar desde muchos lugares o necesitas hacer muchas consultas a ella .. top level collection
si quieres hacer algo que sea intrincico al documento y que no tengas que traer toda la informacion de inicio, si no que hasta que entras al documento (ser mas rapido en red, gastar menos en datos, gastar menos almacenamiento, vallas y traigas la subcoleccion que pertenece a ese documento)
