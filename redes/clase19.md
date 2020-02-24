##Procesamiento de tramas
cada dispositivo conectado a la red se llama host
todos los host tienen una direcion mac que esta relacionada con su tarjeta de red NIC , que es unica
el viaje de una trama desde que sale desde un dispositivo hasta que es encontrado por el dispositivo de destino

1. la direcion mac que esta en el hadware se copia a la memoria ram del dispositivo (host)
2. cuando mandamos un mensaje del dispositivo (host) a otro dispositivo
   - se asigna una direcion de origen y se le asigna tambien la direcion de destino
   - y la trama (frame) va empezar a preguntar a cada host cual es la direcion de destino, la nic del dispositivo de destino detecta que esta es su direcion mac que tiene almacenada en la ram, va compara que es la misma direcion
     los envios de datos a traves de los medios usando las direciones mac y haciendo una combinacion, con direciones mac y direciones IP (direciones fisicas con direciones logicas) que se hacen atraves del protocolo ARP

Estos se pueden hacer de diferentes maneras:

- podemos hacer envios por unicast: solo lo enviaremos a un host (vamos hacer la convinacion de la direcion mac con IP) enviandole el paquete a un solo dispositivo
- posemos hacer envios por multicast: seleccionamos un grupo y enviamos informacion a solo ese grupo (con la combinacion mac/ip)
- posemos hacer envios por difusion (broadcast): son envios que se envian a todos los mienbros de la red, es decir el frame pasa por cada uno de los host preguntando si conincide la direcion mac de destino
