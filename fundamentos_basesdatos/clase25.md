##Creando Platziblog: tablas dependientes
vamos a empezar con las que tienen dependencia o llave foranea o relacion con algunas que ya hemos creado
El comando “cascade” sirve para que cada que se haga un update en la tabla principal,
se refleje también en la tabla en la que estamos creando la relación.
el check no estandar en todos los manejadores (pero es poderosa)

creando la tabla post con la llave foranea

1. creamos la tabla

```sql
CREATE TABLE `platziblog`.`posts`(
	`id` INT NOT NULL AUTO_INCREMENT,
	`titulo` VARCHAR(130) NOT NULL,
	`fecha_publicacion` TIMESTAMP NULL,
	`contenido` TEXT NOT NULL,
	`estatus` CHAR(8) NULL DEFAULT 'activo',
	`usuario_id` INT NOT NULL,
	`categoria_id` INT NOT NULL,
	PRIMARY KEY (`id`)
);
```

2. creando la refencia de llave foranea
   no action es no hacer nada, cuando se rompa la relacion
   casacade cambia cada vez que se haga un update alla, también cambie (CASCADE) igual con delete o borrar
   retric no te permite hacer cambios hasta que resuelvas conflictos

```sql
ALTER TABLE `platziblog`.`posts` (crea la tabla posts)
ADD INDEX `posts_usuarios_idx` (`usuario_id` ASC); (agrega un indice (posts_usuarios_idx) al coampo de usuario_id)
;
ALTER TABLE `platziblog`.`posts` (altera la tabla)
ADD CONSTRAINT `posts_usuarios` (agrega un constraint que llamamos posts_usuarios)
	FOREIGN KEY (usuario_id) (con la llave foranea usuarios_id)
	REFERENCES `platziblog`.`usuarios` (`id`) (con las refencia a la tabla usuarios atraves del campo id)
	ON DELETE NO ACTION (en una borrada ,no quiero que hagas nada)
	ON UPDATE CASCADE; (en una actualizacion, que repercuta al otro lado tambien)
```

```sql
ALTER TABLE `platziblog`.`posts`
ADD INDEX `posts_categorias_idx` (`categoria_id` ASC);
;
ALTER TABLE `platziblog`.`posts`
ADD CONSTRAINT `posts_categorias`
	FOREIGN KEY (`categoria_id`)
	REFERENCES `platziblog`.`categorias` (`id`)
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```
