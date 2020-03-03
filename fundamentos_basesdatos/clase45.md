de bd relacional a documentos

tabla usurio (entidad)
no existe un modo correcto

si es muy importante para ti consultar una lista de usurios a cada rato NO tiene much sentido que lo coloques como una subcoleccion
si quiero sacar una lista de usurios y los usurios solo existen en cada post.. tengo que ir a cada post tengo que ir a subcoleccion de usurios y tengo que ver que usurios hay en la coleccion
no necitas hacer una lista de usurios, relacionados a otra cosa entonces vale la pena tenerlo dentro de un documento

Tabla post
pueden ser un top level conection o subcoleccion de otra coleccion... puede ser parte de una categoria y la categoria ser la top level coleccion o puede ser una top level conection
categoria puede ir dentro del post
ambas son correctos

tener toda la informacion en 1 vista
si en sistema requieres ver el blogpots y esa misma vista tienes que tener todos los datos del blogpots, pero tambien los datos del usuario quien los creo
pero tambien tienes que tener los datos de que categoria pertenece
en este caso vale la pena guardar todo dentro del documento como su coleccion

si por el contrario necitas las categorias y relacionarlas con otra cosa VALE la pena tenerlas por fuera del documento de blogpots

Comentarios tabla van a ir completamente ligados a los post, no es necesario saber de donde viene
el comentario solo existe dentro del blogpots lo guardamos directamente ahy

categoria es intrincado, podemos ser la categoria luego el post, relacionarlas con comentario

en etiquetas podemos meterla como una subcoleccion de los post

estas bd estan pensadas para mantener el estado de tu app

si quieres hacer un query sencillo puedes ponerla como una top level collection
