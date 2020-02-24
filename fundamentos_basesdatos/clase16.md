##Clientes graficos

cuando iniciamos el cliente grafico de mysql workbench por default te viene una conexion local
te pide:

- conection name:
- conection method
- hostname 127.0.0.1 port 3306
- username root
- password
- default shema

las bases de datos tambien se llaman schemas

- create schemas .. es crear una base de datos
- podemos elegir en que secuencia de caracteres lo queremos: pudemos ponerlo default o podemos poner utf8, si quieres algun idioma para que la base de datos maneje algunos simbolos
- collation : default collation

comando:

```sql
CREATE SHEMA `platziblog` DEFAULT CHARACTER SET utf8;
```
