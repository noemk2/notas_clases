##Creando Platziblog: tablas independientes
Una buena práctica es comenzar creando las entidades que no tienen una llave foránea.
Generalmente en los nombres de bases de datos se evita usar eñes o acentos para evitar problemas en los manejadores de las bases de datos.

## 1 crear un nuevo schema

```sql
CREATE SCHEMA 'platziblog';
```

## 2 crear tabla categoria

```sql
CREATE TABLE 'platziblog'.'categorias'(
	'id' INT NOT NULL AUTO_INCREMENT,
	'nombre_categoria' VARCHAR(30) NOT NULL,
	PRIMARY KEY ('id')
);
```

## 3 crear tabla etiquetas

```sql
CREATE TABLE 'platziblog'.'etiquetas'(
	'id' INT NOT NULL AUTO_INCREMENT,
	'nombre_etiqueta' VARCHAR(30) NOT NULL,
	PRIMARY KEY ('id')
);
```

## 4 crear tabla usuarios

```sql
CREATE TABLE 'platziblog'.'usuarios'(
  'id' INT NOT NULL AUTO_INCREMENT,
  'login' VARCHAR(30) NOT NULL,
  'password' VARCHAR(32) NOT NULL,
  'nickname' VARCHAR(40) NOT NULL,
  'email' VARCHAR(30) NOT NULL,
  PRIMARY KEY ('id'),
  UNIQUE INDEX 'email_UNIQUE' ('email' ASC)
);
```

##Creando Platziblog: tablas dependientes

El comando “cascade” sirve para que cada que se haga un update en la tabla principal, se refleje también en la tabla en la que estamos creando la relación.

## 5 creando la tabla post (luego crear la llave foránea)

```sql
CREATE TABLE 'platziblog'.'posts'(
	'id' INT NOT NULL AUTO_INCREMENT,
	'titulo' VARCHAR(130) NOT NULL,
	'fecha_publicacion' TIMESTAMP NULL,
	'contenido' TEXT NOT NULL,
	'estatus' CHAR(8) NULL DEFAULT 'activo',
	'usuario_id' INT NOT NULL,
	'categoria_id' INT NOT NULL,
	PRIMARY KEY ('id')
)
```

## 5 creando la tabla post (luego crear la llave foránea)

cascade sirve para que los cuando cambiamos la llave foránea de una cambia en la otra, solo cuando ocurre un update o delete
set null, cuando update al usuario el usuario va ser nulo
restric es una medida de seguridad para update o delete

## 5 creando la llave foránea usuario_id

```sql
ALTER TABLE 'platziblog'.'posts'
ADD INDEX 'posts_usuarios_idx' ('usuario_id' ASC);
;
ALTER TABLE 'platziblog'.'posts'
ADD CONSTRAINT 'posts_usuarios'
	FOREIGN KEY ('usuario_id')
	REFERENCES 'platziblog'.'usuarios' ('id')
	ON DELETE NO ACTION
	ON UPDATE CASCADE;
```

## 5 creando la llave foránea categoria_id

```sql
ALTER TABLE 'platziblog'.'posts'
ADD INDEX 'posts_categorias_idx' ('categoria_id' ASC);
;
ALTER TABLE 'platziblog'.'posts'
ADD CONSTRAINT 'posts_categorias'
	FOREIGN KEY ('categoria_id')
	REFERENCES 'platziblog'.'categorias' ('id')
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

##Creando Platziblog: tablas transitivas
Las tablas transitivas sirven como puente para unir dos tablas. No tienen contenido semántico.
Reverse Engineer nos reproduce el esquema del cual nos basamos para crear nuestras tablas. Es útil cuando llegas a un nuevo trabajo y quieres entender cuál fue la mentalidad que tuvieron al momento de crear las bases de datos.

## 6 Creando tabla de comentarios

```sql
CREATE TABLE 'platziblog'. 'comentarios' (
	'id' INT NOT NULL AUTO_INCREMENT,
	'cuerpo_comentario' TEXT NOT NULL,
	'usuario_id' INT NOT NULL,
	'post_id' INT NOT NULL,
	PRIMARY KEY ('id')
);
```

## 6 Creando tabla de comentarios llaves foránea usuario_id

```sql
ALTER TABLE 'platziblog'.'comentarios'
ADD INDEX 'comentarios_usuario_idx' ('usuario_id' ASC);
;
ALTER TABLE 'platziblog'.'comentarios'
ADD CONSTRAINT 'comentarios_usuario'
	FOREIGN KEY ('usuario_id')
	REFERENCES 'platziblog'.'usuarios'('id')
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

## 6 Creando tabla de comentarios llaves foránea post_id

```sql
ALTER TABLE 'platziblog'.'comentarios'
ADD INDEX 'comentarios_post_idx' ('post_id' ASC);
;
ALTER TABLE 'platziblog'.'comentarios'
ADD CONSTRAINT 'comentarios_post'
	FOREIGN KEY ('post_id')
	REFERENCES 'platziblog'.'posts'('id')
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

## 7 creando la tabla post_etiquetas (tabla para romper muchos a muchos)

```sql
CREATE TABLE 'platziblog'.'posts_etiquetas'(
	'id' INT NOT NULL AUTO_INCREMENT,
	'post_id' INT NOT NULL,
	'etiqueta_id' INT NOT NULL,
	PRIMARY KEY ('id')
);
```

## 7 creando las llaves foránea de la tabla etiquetas

```sql
ALTER TABLE 'platziblog'.'posts_etiquetas'
ADD INDEX 'postsetiquetas_post_idx' ('post_id' ASC);
;
ALTER TABLE 'platziblog'.'posts_etiquetas'
ADD CONSTRAINT 'postsetiquetas_post'
	FOREIGN KEY ('post_id')
	REFERENCES 'platziblog'.'posts'('id')
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

## 7 creando las llaves foránea de la tabla etiquetas

```sql
ALTER TABLE 'platziblog'.'posts_etiquetas'
ADD INDEX 'postsetiquetas_etiquetas_idx' ('etiqueta_id' ASC);
;
ALTER TABLE 'platziblog'.'posts_etiquetas'
ADD CONSTRAINT 'postsetiquetas_etiquetas'
	FOREIGN KEY ('etiqueta_id')
	REFERENCES 'platziblog'.'etiquetas'('id')
	ON DELETE NO ACTION
	ON UPDATE NO ACTION;
```

## reverse eneguire
