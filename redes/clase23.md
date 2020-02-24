##Procesamiento de tramas
como es que un mensaje es enviado atraves de diferentes dispositivos
La trama es el ultimo pdu que es enviado por los medios
La trama es la pdu de la capa de enlace de datos (la capa de enlace de datos se encarga de hacer la coneccion logica con la parte fisica)
La trama es un pdu que depende del medio, este pdu va cambiar ( lo que se agrege o quitar informacion(datos) deacuerdo al medio que va ser enviado) :

- la trama llega con la informacion(datos) de la capa de aplicacion (donde se generan los datos)
- pasa por la capa de transporte (se identifica como va ser enviado ese mensaje)
- y luego en la capa de red se asigna las direcciones IP
- de ahy ya pasa por un proceso la capa enlace de datos identifica por cual medio voy a enviar esto(datos)

A patir de ese medio este asigna:

- direcciones mac
- informacion relacionanda a ese medio

luego sale (en bit) se convierte en el tipo de señal que va ser enviado
el receptor hace el proceso inverso (transforma denuevo las señales) (para volver a codificarlas)
Hasta que volvamos a tener los datos en el formato que la aplicacion lo necesita

##Para que esa trama viaje de una red a otra, tiene que pasar por diferentes routers en el mundo

funciones de la capa de red:

- encasulamiento
- enrutamiento
- direcionamiento

Para que alla cominacion de capa 2(cominacion en redes locales) hay 2 datos muy necesarios:

1. IP
2. Mascara de Red

Para que alla comunicacion de capa 3 (comunicarnos entre diferentes redes) debemos contar con 3 datos:

- direccion IP
- La mascara de subredo
- el gateway o puerta de enlace predeterminada

Como es que se traza esa ruta desde que hacemos esa solucitud hasta que es encontrado el servidor

el gateway es un ruta por defecto que se le asigna a un equipo y tiene como funcion eviar cualquier paquete del que no conozcamos por cual interfaz enviarlo y no este definido en las rutas del equipo
es muy similar al ARP en capa enlace de datos
pero en esta tabla tenemos un campo que le ayuda al router a determinar cual es el siguiente salto
tabla de enrutamiento: este tabla tiene un campo que tiene el siguiente salto, cual es el siguiente dispositivo por defecto al que el siempre debe enviarle

la tabla tiene 2 caracteristicas principales:

1. "ese" protocolo de ARP conoce siempre que todos los dispositivos esten conectados a la red local
   - cada uno de esos routers (tiene acceso) a todos los dispositivos que tienen conectado a su red local
   
los 3 elementos que contienen una tabla de enrutamiento del router:
- IP
- Mascara de subred
- Direccion del siguiente salto
