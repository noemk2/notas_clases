Capa de enlace de datos: Elementos, funciones
tiene 2 subcapas (capa de enlace de datos)

1. Mac
2. LLC

funciones de la capa de enlace de datos

1. Gestion del canal
   - la capa va contar con protocolos que le permite a la señal decidir si va en un solo canal, si es duplex, o si es duplex
2. Segmentacion de la trama
   - el tamaño del mensaje no puede ser ni muy grande ni muy pequeño, no podemos mandar una cantidad superior a 1518 bytes (a traves de los medios) ni menos de 64 bytes
3. Control de errores
	- cuando los bit salen del emisor (salen organizados) la capa fisica los va agarrar y los va a convertir, que pasa cuando llegan? cuando llegan, llegan desordenados, lo que se encarga la capa enlace de datos es de tomar eso y organizarlos, codificar denuevo de forma que los 2 puedan recivir el mismo mensaje
4. Control de flujo
5. Recuperacion de fallos
