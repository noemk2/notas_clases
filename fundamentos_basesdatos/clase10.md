normalizando platziblo

el diagrama ER se caracteristica por figuaras (cuadrados, rombos) verbos como relaciones

el diagrama Fisico se caracteristica por colocar la entidad y los atributos:ejm: id, login, password, nickname, email,
Con sus tipos de datos y sus cosntrains: integer(PK), varchar(30) NN , varchar(32) NN, varchar(40)NN, varchar (40) unique
en la entidad post: sus atributos : id integer (PK), titulo: varchar (150), fecha_publicacion: timestamp, contenido text, estatus char(8) check(in (activo, inactivo))
en la entidad comentarios: id integer (PK) comentarios TEXT
en la entidad categoria: id integer(PK), categoria varchar(30)
en la entidad etiquetas: id integer(PK), nombre etiquetas varchar(30)

vamos a ver las relaciones, ya no en el rombo sino con los conectores que vimos en el diagrama de cardialidad
la regla es
cuando tengas 1 a 1 no importa a quien le pongas referencia de la otra tabla es indistinto
cuando tengas 1 a N es importante que la tabla donde tienes la terminacion muchos en esta tabla se colocara la llave foranea, esto nos permite guardar la informacion de modo que no se pierda nada
cuando tengas N a N se rompe la relacion NaN poniendo una tabla intermedia (tabla pivote) esta tabla va tener las 2 llaves de las 2 tablas
si bien es cierto que nesecitamos una clave unica para cada registro en este caso tenemos una forma natural de hacerlo, hacer una clave compuesta
una clave compuesta es cuando tu tienes un campo id pero no es un solo campo, el campo id esta formado por 2 campos (el id post y etiquetas) las 2 forman la llave principal de la tabla, aveces es mejor agregar una llave artificial agregada
