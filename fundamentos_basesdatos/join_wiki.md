#join

la sentencia join de sql permite combinar registros de un o mas tablas en una base de datos. En el lenguaje de consultas estructurado (SQL) hay tres tipos de JOIN

- El interno
- El externo
- El cruzado

EL standar ANSI del SQL especifica cinco tipos de JOIN:

INNER
LEFT OUTER
RIGHT
OUTER
FULL OUTER
CROSS

Una tabla puede unirse a si misma, produciendo una auto-combinacion
SELF-JOIN

Matematicamente, JOIN es composicion relacional, la operacion fundametal en el algebra relacional, y, generalizando, es una funcion de composicion

##Tablas de ejemplo
##Combinacion interna (INNER JOIN)
Con esta operacion cada registro en la tabla A es cominado con los correspondientes de la tabla B que satisfagan las codiiciones que se especifiquen en el predicado del JOIN. Cualquier registro de la tabla A o de la tabla B que no tenga uno correspondiente en la otra taabla es excluido, y solo apraceran los que tengan correspondiencia en la otra tabla. Este es el tipo de JOIN mas utlixado, poer lo que es considerado el tipo de combinacion predeterminado

SQL:2003 especifica dos formas difrentes para expresar estas combinaciones. La primera, conocida como explicita, usa la palabra JOIN junto con las condiciones despues de la palabra reservada ON. La segunda es implicita y usa las comas para separar las tablas a combinar en la sentencia FROM, y se usa la sentencia where para establecer las condiciones, la cual estonces es obligatoria para el INNER JOIN pues de lo contrario la sentencia seria CROSS JOIN

Es necesario tener especial cuidado cuando se combina columnas con valores nulos NULL, ya que el valor nulo no se combina con otro valor o con otro nulo, except cuando se le agregan pridicados tales como IS NULL o IS NOT NULL

Como ejemplo, la siguiente consulta toma todos los registros de la tabla Empleado y encuentra todas las combinaciones en la tabla departamento. La sentecia JOIN compara los valores en la columna IDDepartamento en ambas tablas. CUando no existe esta correspondenciia entre algunas combinaciones, estas nose muestran; es decir que si el numero de departamento de un empleado no coincide con los numeros de departamento de la tabla departamento, no se mostrará el empleado con su respectivo departamento
en la tablaresultante

las dos consultas siguientes son similares y se realizan de manera explicita (A) e implicita (B)

Ejemplo de la sentecia INNER JOIN explicita:

```slq
 SELECT *
 FROM   empleado
        INNER JOIN departamento
           ON empleado.IDDepartamento = departamento.IDDepartamento
```
