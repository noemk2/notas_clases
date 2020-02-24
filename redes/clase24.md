Protocolo IP Asignación de direcciones IP, máscara de bits
ahora que ya savemos como son enviados los mensajes, atraves de diferentes medios y atraves de diferentes dispositivos que nos permiten conectarnos entre diferentes redes

El protocolo IP
Es un protocolo que nos permite hacer el direccionamiento y el enrutamiento de los mensajes atraves de la red
El protocolo IP a traves de diferentes algoritmos se encarga de trazar la ruta (la mejor ruta , la mas eficiente)para que los mensajes llegen de un destino a otro

El enrutamiento: Consiste en encontrar un camino que conecte una red con otra, ya vimos que esto se hace a traves de la tabla de enrutamiento de los routers
EL direccionamiento: Se refiere a la foma en que se asigna las direcciones ip a los diferentes dispositivos, por ejemplo la creacion de subredes
la direccion que se le asigna a un dispositivos es una direcion IP

Direccion IP: Es un identificador logico de las interfaces de red de los dispositivos que utilizan protocolo IP para la comunicacion

IPv4 - 32bits - 192.168.1.1
IPv6 - 128bits - hexadecimal

Las direcciones IP podemos separalos en 3 clases (ipv4)
estas separaciones nos permitira es identificar rapidamente cual es la mascara de subred

1. clase A
   redes que se utilizan en areas metropolitanas

   - El primer octeto identifica la red
   - Tres ultimos octetos (24bits) pueden ser asignados a los hosts
   - Cantidad maxima de host es 2̣\*24 - 2

2. clase B

   - Dos primeros octetos para identificar la red
   - Dos octetos finales (16 bits) para que sean asignados a los hosts
   - Cantidad maxima de hosts por cada red 2\*16 - 2
   - 65534 hots

3. clase C

   - Tres primeros octetos para identificar la red
   - Octeto final (8 bits) para que sea asignado a los hosts
   - Cantidad maxima de host por cada red es 2\*8 - 2
   - 254 hosts

para evitar el desperdicio de cantidad de direcciones IP; para evitar se usan tecnicas de asignacion variable de la mascara de subred

La mascara de subred es forma facil de identificar a simple vista cual es la porcion que esta asignada para la identificacion de la red y
Cual es la porcion de la IP que esta designada para los host

Clase A
255.0.0.0 o 11111111.0000000.00000000.0000000
Clase B
255.255.0.0
Clase C
255.255.255.0
para identificar un mascara de subred: cuando ves que 255.0.0.0
255 indica los bit que identifican la red
 indica los bit que identifican la red indica los bits que identifican los host

asignar mascaras variables
