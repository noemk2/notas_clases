Entidades de Platzi Blog
Nuestro proyecto será un manejador de Blogpost. Es un contexto familiar y nos representará retos muy interesantes.

Primer paso: Identificar las entidades
Segundo paso: Pensar en los atributos

entidades platziblog
las entidades son cualquier objeto del mundo real (virtual) que se pueda identificar en un grupo

- usuarios
- comentarios
- posts
- categorias

analizando la entidad post; que tiene un post que le hace ser un post o que tiene para crearlo

- un post tiene
  -un titulo y ese titulo puede ser cualquier cosa mientras sea una serie de caracteres y es justamente lo que identifican al usuario cuando lo vea y lo llama la atencion
- fecha de publicacion, dice que tan actual es el contenido del post
- contenido, la parte importante, lo que consumimos nosotros
- status puede ser activo o inactivo (publicado o no publicado)
- etiquetas, podemos clasificarlos por categorias (se reprenta con doble circulo)
- id necesitamos un atributo clave que nos ayude a diferenciar que un posts es diferente a otro

ahora analizando los atributos de la entidad usuarios

- login nombre de usuario
- password
- apodo
- email es unico
- id, muchos cometemos el error de poner el email como id, pero cuando el usuario quiera cambiar su email, vamos a tener problemas en indentificar todo loque tenia ligado (se aconseja colocar una clave artificial, aparte del email del usuario)
