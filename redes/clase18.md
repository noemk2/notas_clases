Trama de enlace de datos y direcciones mac

El protocolo ethernet se encarga de la gestión de direcciones físicas que nos ayudan a conectar con la capa lógica y la capa física. Está compuesta por un encabezado (direcciones físicas), datos (traen información de la capa de red y la capa de transporte) y trailer

la capa enlace de datos es el capa que conecta la parte física con la parte logica

## trama de ethernet

el pdu de esta de est capa de enlace de datos se llama trama o frame y se conforma por 3 partes principales:

1. Encabezado
   - estaran las direcciones físicas de los dipositivos (direcciones mac), trae la direccion de origen y de destino
2. Datos

   - estos datos han pasado la parte de encaczulamiento (ya han pasado por un capa de transporte, en donde fueron agregados otros protocolos, se definio si estos estaban viajando por udp o por tcp (se agregaron los puertos) y de ahy paso a ser empaquetado en la capa de red, en la capa de red se agrego información logica de las direcciones de destino y de origen del mensaje)
   - ahora esto llega y es empaquetado denuevo y ahora va estar en una trama/frame en donde tambien contine las direcciones fisicas de los dispositivos

3. Trailer (cola)

   - FCS Frame Check Sequence: este va tener unos bits que nos van ayudar a indentificar y la trama llego, si el tamaño es correcto, si llego bien, si llego completa, FCS es un numero que se calcula a partir de los datos que nos ayudan a indentificar si los datos llegan correctos o no
   - una de las cosas que tambien hace la capa enlace de datos es el tema de la sincronizacion
   - Stop Frame

   ## Que es Mac

   es la direccion fisica que tiene la tarjeta de red, todos los dispositivos tienen direccion mac, esta es un indentificador unico, cada dispositivo tiene una direcion mac
   es una direcion fisica que se asigna cuando se manofactura esa tarjeta de red
   los primeros 3 bites indican quien fue que manufacturo la tarjeta tambien conocido como OUI(Organisational Unique Identifier)
   Y los ultimos 3 bites son los que indentifican esa tarjeta de red
