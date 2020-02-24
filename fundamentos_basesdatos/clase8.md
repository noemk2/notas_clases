##Diagrama Físico: tipos de datos y constraints
el diagrama Entidad Relacion (ER) nos ayuda a conceptualizar mentalmen y graficamente todos los actores, las entidades y relaciones que intervienen en este sistema
tenemos ya bien definido cuales son las partes que van a interactuar y de que manera

sin envargo para llevarlo a la practica tenemos que llevarlo mas alla
que tipo de detalle?

- nos falta agregar algunos parametros (que nos ayuden a despues deducirlo facilmente a lo que esto la base de datos realmente va entender)

Para esto vamos a utilizar otro diagrama que se deriva del anterior (ER)

- Diagrama Fisico: cuando estabamos estudiando cardilialidad vimos la forma en que usumos los conectores para simbolizar las relaciones y su cardilialidad en un diagrama fisico\*
- Ahora vamos a aplicarlo (simbolizar)

Para llevar a la práctica un diagrama debemos ir más allá y darle detalle con parámetros como:

Primero se revisa los tipos de datos
Tipos de dato:

Texto: CHAR(n), VARCHAR(n), TEXT (te permite almacenar caracteres no solo 1, te permite almacenar cadenas )(varchar es similar y te permite almacenar cadenas) (la diferencia: Cuando surgieron las bases de datos trataron de optimizar el uso de memoria, la diferencia esque el tipo de dato chart toma un pedacito de memoria del numero de caracteres que vas a guardar y reservarlo para tu solamente puedas ocupar) (varchar almacena de manera dinamica; el espacio de memoria y apartir de ahy iva
encojiendose, hasta el maximo que declarabas, para permitirte almacenar cadenas mas largas y mas chicas esto lo hacia mas eficiente cuando no conocias el tamaño de la cadena (si podia hacer una cadena de 2 caracteres o 100))
text es un tipo de dato que igual nos sirve para almacenar cadenas pero son cadenas muy grandes (varchar tiene un limite 255 caracteres) text nos entrega caracteres mas como 500 o mas, este lo utilizaremos para guardar el contenido de nuestro post

Números: INTEGER, BIGINT, SMALLINT, DECIMAL(n,s), NUMERIC(n,s), integer quiere decir el numero que no tiene punto decimal o no tiene fracion, esto nos sirve cuando tu quieres hacer una suma resta multiplicacion, la base de datos entiende que se trata de una base de datos (no una cadea) cuando queremos usar un numero muy grande utilizamo BIGINT y cuando es un numero de 99 o menos utilizamos SMALLINT, DECIMAL y NUMERIC recive 2 parámetros (numero, numeros decimales) de este modo puedes declarar un
numero mas preciso (operaciones con monedas, fraccionarias)
Fecha/hora: DATE, TIME, DATETIME, TIMESTAMP ademas de determinar la fecha, nos sirve para saber cuando publico un registro, cuando lo publico, modifico, el tipo de dato DATE solo contine la fecha (año mes y dia) TIME que contine la hora del dia de las 24 horas, DATETIME y TIMESTAMP que ambos tiene el dia como la hora, incluso a milisegundos se usa cuando quieres guardar algo con mucha precision
Lógicos: BOOLEAN significa que solo puede tener 2 tipos de datos (cierto o falso, 0 o 1)
Constraints (Restricciones) para completar el diagrama fisico es Constraints o restricciones esto son reglas del tipo de datos
hay muchos tipos de constraints

NOT NULL: Se asegura que la columna no tenga valores nulos. Cuando tu metes un registro o una serie de datos a una tabla, el valor por defecto es un valor nulo o null, lo que estas asiendo con esta regla esque en esta columna particular (ejm nombre) esta columna que lleve nombre no permiteremos que valla en blanco se agrega el constraints not null, si te tratan de mandar un registro que no viene el nombre de la persona, la base de datos mandara un error, te obliga a poner datos
UNIQUE: Se asegura que cada valor en la columna no se repita, nos asegura que el valor es unico en nuestra tabla, un ejem es en los ususarios es el email, en una tabla de usuarios queremos que nadie tenga el mismo email 2 veces,
PRIMARY KEY: Es una combinación de NOT NULL y UNIQUE, cuando tenemos que identificar de manera unica los registros que existen en una tabla, esto lo hacemos atraves de una campo clave o llave, esta nos da una serie de ventajas: 1ro es NOT NULL y es PRIMARY KEY (ambos) es decir si lo metemos nos dara errores porque estamos metiendo valores nulos y si hay repetivos ... error, ademas el PRIMARY KEY nos ayudara posteriormente hacer la union de una tabla a otra (entidad a otra) automaticamente al
declarar un campo como PRIMARY KEY lo estamos haciendo un indice

FOREIGN KEY: Identifica de manera única una tupla en otra tabla (llave foranea) cuando queremos juntar 2 tablas y decir que esta tabla esta relacionada con esta otra (lo que estamos diciendo esque la primary key se añade como llave foranea en la otra) tiene que tener las mismas caracteristicas que la primary key (tiene que ser del mismo tipo) pero en este caso no puede ser unica porque nuestra llave foranea si se puede repetir

CHECK: Se asegura que el valor en la columna cumpla una condición dada, algunas bases de datos quitaron este tipo de constraints, pero las que lo utilizan son muy potentes check nos permite hacer la regla que queramos, check definir una regla que hace un simil con el mundo real y que nos permite justamente hacer reglas de negocio o reglas que obedescan a lo que nuestro cliente o nuestro caso de uso nos esta pidiendo, ejm dejame entrar registros que sean activos e inactivos, ejmplo en el estado
de nuestros blogpost podemos tener activo e inactivo pero no queremos
DEFAULT: Coloca un valor por defecto cuando no hay un valor especificado, por defecto es null
cuando alguien quiere mandar al registro un valor 0, en vez de meter un valor nulo, lo va convertir por default en 0

INDEX: Se crea por columna para permitir búsquedas más rápidas, lo que nos permitir es hacer busquedas mas rapidas en nuestra tabla de base de datos, es muy util cuando tenemos muchos registros, el indice tiene una desventaja esque cuando existe un indice en una columna, cada que añadimos registros, se vuelve mas lento porque cada que añades un nuevo registros se tiene indexar todos los robos de la base de datos, el tipo de caso de uso de indice es cuando te interesa estar sacando datos de la
base de datos continuamente pero no metes datos nuevos tan seguido
ejm: cuando un indice es contraproducente: cuando tienes una tabla y estas metiendo muchos registros pero no lees tan constantemente
