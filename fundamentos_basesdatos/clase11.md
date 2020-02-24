Formas normales en DB relacionales

la normalizacion en las bases de datos relacionales es uno de esos temas que, por un lado es sumamente importante y por el otro suena algo isoterico. Vamos atratar de entender las fomas normales (FN) de una manera simple para que puedas aplicarlas en tus proyectos profesionales

Primera forma Normal (1FN)
Esta FN nos ayuda a eliminar los valores repetidos y no atomicos dentro de una base de datos

Formalmente, una tabla esta en primera forma normal si:

- Todos los atributos son atomicos. Un atributo es atomico si los elementos del dominio son simples e indivisibles
- No debe existir variacion en el numero de columnas
- Los campos no clave deben identificarse por la clave (dependencia funcional)
- Debe existir una idenpendencia del orden tanto de las filas como de las columnas; es decir, si los datos cambian de orden no deben cambiar sus significados

Se traduce basicamente a que si tenemos campos compuestos como por ejemplo "nombre_completo" que en realidad contiene varios datos distintos, en este case podria ser "nombre", "apellido_paterno", "apellido materno", etc
Tambien debemos asegurarnos que las columnas son las mismas para todos los registros, que no ha registros con columnas de mas o menos

Todos los campos que no se consideran clave deben depender de manera unica por el o los campos que si son clave

Los campos deben ser tales que si reordenamos los registros o reordenamos las columnas, cada dato no pierda el significado

##Segunda Forma Normal(2FN)
Esta FN no ayuda diferenciar los datos en diversas entidades
Formalmente, una tabla esta en 2da forma normal si:

- Esta en 1FN
- Si los atributos que no foman parte de ninguna clave dependen de forma completa de la clave principal. Es decir, que no existen dependencias parciale
- Todos los atributos que no son clave principal deben depender unicamente de la clave principal
  Lo anterior quiere decir que si tenemos datos que pertenecen a diversas entidades, cada entidad debe tener un campo clave separado. Por ejemplo

- Tercera Forma Normal (3FN)
  Esta FN nos ayuda a separar conceptualmente las entidades que no son dependientes

Formalmente, una tabla esta en tercera forma normal si:

- Se encuentra en 2FN
- No existe ninguna dependencia funcional transitiva en los atributos que no son clave

Esta FN se traduce en que aquellos datos que no pertenecen a la entidad deben tener una independencia de las demas y debe tener un campo clave propio. Continuando con el ejemplo anterior, al aplicar la 3FN separamos la tabla alumnos ya que contiene datos de los cursos en ella quedando de la siguiente manera

##Cuarta forma Normal (4FN)

Esta FN nos trata de atomizar los datos multivaluados de manera que no tengamos datos repetidos entre rows

Formalmente, una tabla esta en cuarta forma si.

- encuentra en 3FN
- Los camos multivaluados se dientifican por un clave unica

Esta Fn trata de eliminar registros deplucados en una entidad, es decir que cada registro tenga un contenido unico y de necesitar repetir la data en los resultados se realiza a traves de las claves foraneas

Aplicando el ejemplo anterior la tabla materia se independiza y se relaciona con el alumno a atraves de una tabla transitiva o pivote, de tal manera que si cambiamos el nombre de la materia solamente hay qeu cambiarla una vez y se propagara a cualquier referencia que haya de ella

De esat manera, aunque parezca que la informacion se multiplico, en realidad la descompusimos o normalizamos de manera que a un sistema le sea facil de reconocer y manterner la consistencia de los datos

ALgunos autores precisan una 5FN que hace referencia a que despues de realizar esta normalizacion a traves de uniones (JOIN) permita regresar a la data original de la cual partio
