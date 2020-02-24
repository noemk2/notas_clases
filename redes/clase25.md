Direccionamiento IP

Conversion entre binarios y decimales
Asignacion de redes

- Mascar de red
- Direccion de red
- Direccion de broadcast
- Rango asignable
- Subredes

  la capa de red se encarga de hacer todo este direccionamiento de internet

la capa mas cercana a los dispositivos fisicos se llama capa fisica; esta capa nos permite tener acceso a redes locales a traves de medio de coneccion local

la capa de red es la que nos permite esas redes sacarlas de nuestra red local y que estemos conectados a internet
es la que nos permite hacer conecciones wan
se encarga de hacer 4 pasos

esta capa atraves del protocolo ip la que se encarga de hacer esos cuatro pasos
hace el direccionamiento ip
encanzula y desencanzula los mensajes porque cada dispositivo en cada uno de los saltos que hace el mensaje atraves del proceso en el cual viaja cada router (abre el msj determina hacia donde va)

Mascara de red: Nos permite identificar a simple vista la porcion de la direccion IP que se ha asignado a la identificacion de la red y la porcion que se ha asignado a los hosts

Si necesitamos una red para 300 usuarios, resulta que una red de clase C, solo nos da acceso a 256 hosts
no podemos ir a una red de clase b, me da 65000 direcciones, el desperdicio es muy grande, reducir el gasto de direcciones,
Solucion; decirle al segmento de hosts, que le preste unos bits para combertirlo en otras subredes mas pequeñas que uno pueda usar
Ahora sera mas distribuido, y permite hacer segmentos mas pequeños y administriar de mejor manera

Este proceso de pedir prestado a los hosts, se llama Subneting (pedir prestados bits y volver a calcular)

datos necesarios para hacer la asignacion de datos IP

1. Direccion de Red: Porcion de hosts con todos los bits en CERO: es la primera direccion, la direccion absoluta de toda la red, es la direccion que identifica toda la red

   - tiene un caracteristica; la porcion de hosts de nuestra mascara simpre va estar con todos los bits en CERO

2. Direccion de Broadcast: Porcion de hosts con todos los bits en UNO, es la utiliza protocolos como DHCP par hacer difuciones en modo broadcast (medoto para enviar a todos los dispositivos)

3. Rango de direcciones para los dispositivos

## Subredes

Cuando una red es muy grande, conviene dividirla en subredes, por los siguientes motivos:

- Hacer la red mas manejable, administrativamente
- Se puede controlar el trafico entre diferentes subredes

me permite obtimizar el uso de los recursos, basicamente es tomar bits del segmento del hosts
