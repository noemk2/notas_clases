##Capa de RED
recap: vimos como los datos viajan atraves de los medios y como pasan por una capa de enlace (esta se encarga de determinar la relacion entre las direcciones logicas y las direcciones fisicas)
AHORA, vamos a hablar de las direcciones logicas
La capa de red es la que se encarga de enrutar (distribuye) los datos a traves de diferentes redes
Analisis del proceso de cual tiene que pasar un paquete para que sea enviado desde un emisor hasta un receptor, que informacion es la que se agrega en el pdu de la capada de red, cual protocolo permite esta informacion
el protocolo que permite esta comunicacion, es el protocolo IP
La segmetacion de redes en subredes
para la transmision de datos de diferentes redes se lleve a cabo esto se logra por medio del router
El router es el equipo de la capa de red que toma las señales, toma la trama, la desencapsula, la abre, revisa las direcciones de destino y de origen y vuelve a enrutar, vuelve a encapsular la trama y la envia la trama hacia el siguiente punto

##Funciones principales de la capa de red

- Hacer el direccionamiento de paquetes; asigna las direciones logicas a los paquetes; cuando un segmento de la capa de transporte llega a la capa de red se le asigna la direcion ip de origen y la direcion ip de destino
- Encapsulamiento de los paquetes; cuando el router recive una trama, el router abre esa trama, para saber las direciones logicas(encapsulamiento) despues determinar cual es el siguiente salto hacia donde debe ir (donde enviara) cuando ya ha echo ese enrutamiento, vuele y encapsula y envia esa trama, y lo envia al enlace de datos para luego al medio, para llege a otro dispositivo
- Enrutamiento
- Desencapsulamiento de los paquetes

PDU de la capa de red
cuando los datos que fueron generados desde la capa de aplicacion

1. en la capa de transporte se le asigna TCP y los dato
2. en la capa de red se le asigna 3 capos ... tiene mas campos pero estos son las mas importantes
   - 1ro Direccion de origen (ip) (quien esta enviado la solicitud)
   - 2do Direccion de destino (hacia donde queremos enviar este mensaje)
   - 3ro Se le asigna un campo llamado ttl
   - otros, identifica los errores, identifica el medio por que se esta enviando la señal
   - la trama es un pdu que depende del medio por cual se esta enviando, es diferente una trama que se envia por medio de cobre que por un medio de fibra optica

en el caso del pdu de la capa de red no depende del medio

El ttl es un campo muy importante a la hora de enviar un paquete a traves de la red
El ttl (Time to live), Es la cantidad maxima de saltos por los que debe pasar un mensaje hasta que es rechazado
este nos indica la cantidad de saltos que va tomar un mensaje hasta que se determine que no llego a ningun lado
generalmente esta definido como 64 saltos pero se puede modificar
SI ese mensaje salto hasta el limite (64) significa que ese mensaje no va llegar
