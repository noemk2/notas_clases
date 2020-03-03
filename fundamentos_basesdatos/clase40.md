##¿Qué son y cuáles son los tipos de bases de datos no relacionales?

Respecto a las bases de datos no relacionales, no existe un solo tipo aunque se engloben en una sola categoría.

Tipos de bases de datos no relacionales:

Clave - valor: Son ideales para almacenar y extraer datos con una clave única.(estan echas para almacenar datos de manera rapida) Manejan los diccionarios de manera excepcional. Ejemplos: DynamoDB, Cassandra.(se vasan en algoritmos de hash)

Basadas en documentos: (no son archivos)Son una implementación de clave valor que varía en la forma semiestructurada en que se trata la información. Ideal para almacenar datos JSON y XML. Ejemplos: MongoDB, Firestore. (tienen un estructura un poco mas definida)

- si tienes un juego que esten jugando varias personas, el estado actual de esa aplicacion para un usurio lo puedes guardar de una manera sumamente facil y lo puedes restaurar
- si tu tratas de hacer busquedas (querys) y tratas de hacer querys muy complejos, este tipo de base de datos no responde bien
- pero para guardar el estado actual y traerlo, para tener la forma viva de una aplicacion web son sumamente eficientes

Basadas en grafos: Basadas en teoría de grafos, sirven para entidades que se encuentran interconectadas por múltiples relaciones. Ideales para almacenar relaciones complejas. Ejemplos: neo4j, TITAN.

- los grafos nos ayudan a mapear estas relaciones complejas y se usa much en IA (redes neuronales)

En memoria: Pueden ser de estructura variada, pero su ventaja radica en la velocidad, ya que al vivir en memoria la extracción de datos es casi inmediata. Ejemplos: Memcached, Redis.

- son sumamente rapidas con consultas, tienes que estar guardando datos en disco y son volatiles (si tu manejas un servidor o una instancia en cloud, si ese servidor se reicia probablemente tengas que volver a indexar, o volver a traer del disco duro a la memoria, es complicado mantener la sincronia)

Optimizadas para búsquedas: Pueden ser de diversas estructuras, su ventaja radica en que se pueden hacer queries y búsquedas complejas de manera sencilla. Ejemplos: BigQuery, Elasticsearch.

- nos ayudan hacer queries muy complejos en cuestiones muy rapidas de tiempo
- estas bases de datos sirven como grandes repocitorios de datos, muchas veces historicos, al que les puedes preguntar cuestiones muy complejas de negocio, tendencias historicas
- bigquery
- elasticsearch

- las bases de datos relaciones al tener muchos datos empiezan a tener problemas para responder en tiempo y manejar todas las relaciones tan complejas que tiene
