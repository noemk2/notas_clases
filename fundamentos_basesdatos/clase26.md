##Creando Platziblog: tablas transitivas

Las tablas transitivas sirven como puente para unir dos tablas.
No tienen contenido semántico.
Reverse Engineer nos reproduce el esquema del cual nos basamos para crear nuestras tablas.
Es útil cuando llegas a un nuevo trabajo y quieres entender cuál fue la mentalidad que tuvieron al momento de crear las bases de datos.

- creando la tabla de comentarios

```sql
CREATE TABLE `platziblog`.`comentarios` (
	`id` INT NULL AUTO_INCREMENT,
	`cuerpo_comentario` TEXT NOT NULL,
	`usurio_id` INT NOT NULL,
	`post_id` INT NOT NULL,
	PRIMARY KEY (`id`);
)
```

- creando la llave foranea
- creando comentarios_usuario

```sql
ALTER TABLE `platziblog`.`comentarios`
ADD INDEX `comentarios_usuario_idx` (`usuario_id` ASC);
;
ALTER TABLE `platziblog`.`comentarios`
ADD CONSTRAINT `comentarios_usuario`
	FOREIGN KEY (`usuario_id`)
	REFERENCES `platziblog`.`usuario_id` (`id`)
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

- creando comentarios_post

```sql
ALTER TABLE `platziblog`.`comentarios`
ADD INDEX `comentarios_post_idx` (`post_id` ASC);
;
ALTER TABLE `platziblog`.`comentarios`
ADD CONSTRAINT `comentarios_usuario`
	FOREIGN KEY (`usuario_id`)
	REFERENCES `platziblog`.`usuario_id` (`id`)
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

- creando una la tabla artifial de muchos a muchos (esta se llama tabla transitivas porque solo sirve de pibote para unir otras 2 tablas, pero semanticamente no tiene ningun sentido, no tiene informacion propia, solo sirve para ligar)
- creando posts_etiquetas

```sql
CREATE TABLE `platziblog`.`posts_etiquetas` (
	`id` INT NOT NULL AUTO_INCREMENT,
	`post_id` INT NOT NULL,
	`etiqueta_id` INT NOT NULL,
	PRIMARY KEY (`id`)
);
```

- creando la llave foranea
- creando la llave postsetiquetas_post

```sql
ALTER TABLE `platziblog`.`posts_etiquetas`
ADD INDEX `postsetiquetas_post_idx` (`post_id` ASC);
;
ALTER TABLE `platziblog`.`posts_etiquetas`
ADD CONSTRAINT `postsetiquetas_post`
	FOREIGN KEY (`post_id`)
	REFERENCES `platziblog`.`posts` (`id`)
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

- creando la llave postsetiquetas_etiquetas

```
ALTER TABLE `platziblog`.`posts_etiquetas`
ADD INDEX `postsetiquetas_post_idx` (`post_id` ASC);
;
ALTER TABLE `platziblog`.`posts_etiquetas`
ADD CONSTRAINT `postsetiquetas_post`
	FOREIGN KEY (`post_id`)
	REFERENCES `platziblog`.`posts` (`id`)
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

tips: ingenieria inversa: (solo en workbensh)

- database, reverse engineer..
- le damos acceso a donde vamos a conectar
- seleccionamos la base de datos que queremos exportar
- importar todos los objetos de mi base de datos
- imformacion de las tablas importadas

esto es interesante cuando llegas a un nuevo trabajo y te encuentras que la base de datos ya la crearon, ya tiene un tiempo funcionando y tu quieres llegar a entenderla
esto te permite ver el mapa de como se creo esta base de datos y como la persona que la creo, penso y la conceptualizo en su momento
entender la mentalidad que se trae y como se penso en la arquitectura y en la estructura de datos de esa compañia
