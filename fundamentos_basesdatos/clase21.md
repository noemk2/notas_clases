DDL drop
Está puede ser la sentencia ¡más peligrosa! (????), sobre todo cuando somos principiantes. Básicamente borra o desaparece de nuestra base de datos algún elemento.
trata de borrar
en la clase 20 vimos como borrar columnas

```sql
DROP TABLE people;
DROP DATABASE test_db;
```

##Borrando una tabla

```slq
DROP TABLE 'platziblog'.'people';
```

##Borrando una tabla

```slq
DROP DATABASE 'platziblog';
```

con esto concluye las sentencias ddl las sentencias ddl nos ayudaros a manipular, modificar a crear y a borrara la estructura de la base de datos

- nos ayuda a crear la base de datos misma
- nos crea las tablas que hay en ella
- nos crea las vistas que hay en ella
- toda la estructura que tengamos en ella, que va obedecer lo que hallamos analizado se va ver reflegada en la estructura de la base de datos , lo creamos con las sentencias ddl
- estas sentencias van ocupar muy pocas veces, al inicio de un proyecto se crea toda la estructura pero despues se cambia muy poco (hay que darle mantenimiento, agregando algunas tablas, pero es bastante raro)
- lo utilizamos al inicio del proyecto (ddl) pero despues utilizamos dml
