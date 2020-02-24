##Creando Platziblog: tablas independientes

Una buena práctica es comenzar creando las entidades que no tienen una llave foránea.
Generalmente en los nombres de bases de datos se evita usar eñes o acentos para evitar problemas en los manejadores de las bases de datos.

como buena practica:

- empezar por los que no tienen ningua llave foránea (simpre van a la tabla que tiene el final de la linea de muchos, las que tienen en uno generalmente no tienen llave foránea)

pasos para crear nuestro base de datos:

- creamos nuestro esquema (schema)

```sql
CREATE SCHEMA 'platziblog';
```

- creando tablas generalmente en los nombres de bases de datos, tablas, evitamos, el uso de acentos y ñ:

-creando la tabla categorias

```sql
CREATE TABLE `platziblog`.`categorias`(
	`id` INT NOT NULL AUTO_INCREMENT,
	`nombre_categoria` VARCHAR(30) NOT NULL,
	PRIMARY KEY(`id`)
);
```

-creando la tabla etiquetas

```sql
CREATE TABLE `platziblog`.`etiquetas`(
	`id` INT NOT NULL AUTO_INCREMENT,
	`nombre_etiqueta` VARCHAR(30) NOT NULL,
	PRIMARY KEY(`id`)
);
```

- creando la tabla usuarios

```sql
CREATE TABLE `platziblog`.`usuarios`(
	`id` INT NOT NULL AUTO_INCREMENT,
	`login` VARCHAR(30) NOT NULL,
	`password` VARCHAR(32) NOT NULL,
	`nickname` VARCHAR(40) NOT NULL,
	`email` VARCHAR(40) NOT NULL,
	PRIMARY KEY(`id`),
	UNIQUE INDEX `email_UNIQUE` (`email`ASC)
);

```
