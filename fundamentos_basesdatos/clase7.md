Diagrama ER
Un diagrama es como un mapa y nos ayuda a entender cuáles son las entidades con las que vamos a trabajar, cuáles son sus relaciones y qué papel van a jugar en las aplicaciones de la base de datos.
vamos a ver en nuestro ejemplo de base de datos Platziblog, cual es son las entidades que teniamos anteriormente
entidades:

- posts
- usuarios
- categorias
- comentarios
- etiquetas(atributo multivaluado, estos se convierten en etidades separadas)

cuando una etiqueta esta en mas de una notica, realmente tiene una vida propia, porque esta asociado a diferentes entidades y a diferentes blogspot
que relaciones tiene entre ellas

- usuarios muchos escribe posts (1:N)
- usuarios escribe comentarios (1:N)
- posts tienen muchos comentarios(1:N)
- categorias tiene muchos posts (1:N)
- los posts pueden tener muchas etiquetas (N:N)

completado el diagrama inicial para nuestro sistema platziblog
existen varias nomenclaturas utilizadas
este es Entidad Relacion (ER)
