## DDl create

Sql tiene dos grandes sublenguajes :

DDL o data definition language que nos ayuda a crear la base de datos. Existen tres grandes comandos:

- Create: Nos ayuda a crear bases de datos,tablas, vistas, indices. etc
- Alter: ayuda a alterar o modificar entidades
- Drop: Nos ayuda a borrar. hay que tener cuidado al utilizarlo

3 objetos que manipularemos con el lenguaje DDL

- Database o base de datos
- Table o tablas. Son las traduccion a SQL de las entidades
- View o vistas: se ofrece la proyeccion de los datos de la base de datos de forma entendible

## Create Database

### Comandos para crear una base de datos:

- ```sql
  CREATE DATABASE test_db
  ```

- ```sql
  USE DATABASE test_db
  ```

### Comandos para crear una tabla:

```sql
CREATE TABLE people (
person_id int,
last_name varchar(255),
first_name varchar(255),
address varchar(255),
city varchar(255) );
```


