##Relaciones
las relaciones son objetos
Las relaciones nos permiten ligar o unir nuestras diferentes entidades
y se representan con rombos. Por convención se definen a través de verbos.
el diagrama que estabamos haciendo se llama entidad-relacion
las relaciones se representan con un rombo
Las relaciones tienen una propiedad llamada cardinalidad y tiene que ver con números. Cuántos de un lado pertenecen a cuántos del otro lado:

Cardinalidad: 1 a 1
Cardinalidad: 0 a 1
Cardinalidad: 1 a N
Cardinalidad: 0 a N

ejemplo:

tenemos 2 entidades automovil y dueño
el verbo seria : tiene

tenemos 2 entidades: jugadores y equipos
el verbo seria : pertenece

particularidades de las relaciones:

- tenemos 2 entidades: laptops y discos_duros (no era una entidad, es una atributo multivaluado)
- cuando tenemos atributos multivaluados, por lo general los convertimos en etidades separadas, porque tienen una vida por si misma y porque se puede relacionar de varias maneras con laptops
- lo separamos luego por normalizacion
- como definimos cuantos discos_duros tiene la laptop tiene que ver con la propiedad de las relaciones, se llama cardinalidad

cardinalidad: tiene que ver con numeros, comom el ejemplo de la laptop (cuantos de un lado pertenece a cuantos del otro lado)

tenemos diferentes tipos de cardinalidad

- 1 a 1 ejm: 2 entidades: persona, datos_contacto; verbo de relacion: tiene; enunciado: 1 persona tiene 1 serie de datos_contacto; una serie de datos_contacto pertenece a cuantas personas? 1, se simboliza con una doble raya a los extremos del conector
- 0 a 1 ejm: 2 entidades: sescion_actual, usuario; verbo de relacion: tiene; (tambien se le dice 1 a 1 opcional) puede ver la opcion que no exista uno o ninguno de los lados, se representa con la misma linea anterior punteada para indicar que es opcional
- 1 a n ejm: perosona, automovil; verbo de relacion; tiene; quiere decir que de un lado tenemos 1 pero del otro lado tenemos muchos, 1 persona puede tener muchos automoviles, pero 1 automovil solo puede tener un dueño, se representa de un lado una linea (indica uno) del otro una linea se parte en 3
- 0 a n ejm: paciente, hab_hospital; verbo de relacion; tiene; 1 paciente simpre esta asignado a una havitacion de hospital, pero una hab_hospital puede estar vacia tambien (en ese momento puede que no tenga ningun paciente) se representa con el circulito del lado del uno o con la linea punteada
