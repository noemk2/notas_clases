Diagrama Físico: normalización
La normalización como su nombre lo indica nos ayuda a dejar todo de una forma normal.
Esto obedece a las 12 reglas de Codd y nos permiten separar componentes en la base de datos:
las reglas de Codd convierten tu base de datos relacional
en este punto (normalización) donde acabas de hacer tu base de datos, empiezas a desmenuzar, a separar y la dejas en una forma en una completamente normalizada es cuando llegas a un punto zen
cuando lleges hacer esto a tu base de datos llegaras a un punto de experiencia demaciado importante

Primera forma normal (1FN): Atributos atómicos (Sin campos repetidos)  
Segunda forma normal (2FN): Cumple 1FN y cada campo de la tabla debe depender de una clave única.
Tercera forma normal (3FN): Cumple 1FN y 2FN y los campos que NO son clave, NO deben tener dependencias.
Cuarta forma normal (4FN): Cumple 1FN, 2FN, 3FN y los campos multivaluados se identifican por una clave única.
