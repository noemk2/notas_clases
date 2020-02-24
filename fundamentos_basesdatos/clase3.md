##Entidades y atributos
Una entidad es algo similar a un objeto (programación orientada a objetos) y representa algo en el mundo real, incluso algo abstracto. Tienen atributos que son las cosas que los hacen ser una entidad y por convención se ponen en plural.
la idea es que un objeto u entidad lo que representa es algo en el mundo real, cualquier cosa que se te venga a la mente se representa como una entidad
cualquier objeto que se te ocurra podemos convertirlo en una entidad
las entidades se encienrran en rectangulos
igual que los objetos las entidades tienen atributos que son las cosas que le hacen ser una entidad
los atributos se dibujan en ovalos
Los atributos compuestos son aquellos que tienen atributos ellos mismos.
los atributos que tienen que son muchos se representa con un doble ovalo eso quiere decir que es un atributo multivaluado
cuado un atributo esta formado por otras serie de partes ... a este tipo de atributo se le llama atributo compuestos
la antiguedad es un atributo especial no se calcula igual que los demas, la puedes infererir apartir de del dia que salio

Los atributos llave son aquellos que identifican a la entidad y no pueden ser repetidos. Existen: se representa como un ovalo con lineas punteadas
atributo llave: es dato unico (numero de serie) (dato llave) se represena con una linea debajo
los atributos llave exiten 2 grandes tipos; naturales (inherente al objeto), artificial (no viene inherente al objeto en si mismo, por convención se le asigna)
las entidades fuerte son entidades que no dependen de ninguna entidad para existir

Naturales: Son inherentes al objeto como el número de serie
Clave artificial: No es inherente al objeto y se asigna de manera arbitraria.
Entidades débiles: No pueden existir sin una entidad fuerte y se representan con un cuadrado con doble línea

Identidades débiles por identidad: No se diferencian entre sí más que por la clave de su identidad fuerte.
Identidades débiles por existencia: Se les asigna una clave propia.

por convención las entidades se ponen en plural, porque una entidad representan un grupo de estos
las laptop tienen una serie de atributos; pantalla, color año, modelo, no de serie, disco duro, metodo de entrada, antiguedad
el atributo metodo de entrada, es compuesto, y tiene trackpad y teclado
el atributo no de serie, es un atributo que nos ayudara a identificar de forma unica a esa computadora o dentro del grupo de computadora

En el caso de las entidades, los atributos tienen la pecularidad que lo identifican de manera unica, dentro del conjunto -> si tenemos 2 laptops que tienen todos los mismos datos, el dato que los va diferenciar es el dato no de serie (este dato se representara con una linea debajo)

entidades fuertes no dependen de ninguna entidad para existir
entidades debiles no puede existir sin una entidad fuerte
(las entidades debiles se representan con un cuadrado pero tienen doble linea)
(las entidades fuertes se representan con cuadrado con una sola linea)

ejm:
entidad fuerte: libros
entidad debil: ejemplares

Libros ---- ejemplares

Porque ejemplares es una entidad debil de libros?
Respuesta: No puedes tener en un biblioteca un ejemplar de un libro que no tienes necesitas forzosamente, tener un libro para tener varios ejemplares
Si no tienes el libro para empezar, no puedes tener ejemplares en tu biblioteca

Las entidades debiles pueden ser debiles por 2 motivos:

- identidad: quiere decir que no se diferencian entre si mas que por la clave de su entidad fuerte
  ejm:
  cuando tenemos 2 entidades; Libros y ejemplares: - Libros atributos: id titulo ... - Ejemplares atributos: libro id, localizacion, edicion... - en el lado de ejemplares tenemos muchos datos repetidos, para diferenciarlos tenemos que agregarles la clave de libro, y esto las hace dependiente y las hace debil hacia libros - cuando les damos una clave propia, ya no se hacen debiles por identidad, sino por existencia
- existencia: quiere decir que auque agreges un id que es diferente quel de libro y es propio de ejemplares, aun asi coceptaualmente no puedes tener un ejemplar sin ningun libro
  auque no dependa del id de la entidad fuerte aun asi no podemos tener un ejemplar sin ningun libro primero
