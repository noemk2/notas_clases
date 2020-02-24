##Protocolo de resolución de direcciones ARP
con una convinacion de direcion mac y ip podemos hacer diferentes formas de envio
Para enviar diferentes paquetes se Usa ARP
Este protocolo tiene 2 funciones:

1. resuelve las relaciones de direciones IP y mac
   - cada host tiene tiene una tabla de cache arp
2. mantine actulizada la tabla
   - hace una solicitud (envia un paquete) a todos los host conectados en esa red, pregunta si lo tiene almacenada la mac, sino pregunta la direccion mac y este le contesta con otro paque donde le envia la direcion mac, asi.. esque el protocolo ARP mantiene actulizada la la direcion IP con la direcion mac de cada dispositivo que este conectado dentro de la lan
