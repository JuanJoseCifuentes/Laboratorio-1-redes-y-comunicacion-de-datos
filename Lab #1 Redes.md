# Introducción
Las redes son las que hacen posible para nosotros comunicarnos con el resto del mundo. De no ser por la enorme red que recorre todo el mundo, y por las redes más pequeñas que la componen, no seríamos capaces de acceder al internet, el cual ha llegado a convertirse en una necesidad básica hoy en día. 
Para que las redes funcionen es necesario tener dos componentes, el componente del Hardware y el componente lógico. Las redes están compuestas por nodos terminales y nodos intermedios que se comunican por medios de transmisión de datos, que pueden ser cables o medios inalámbricos. La comunicación entre estos dispositivos es regulada por una serie de protocolos que permiten el correcto manejo de la información y una estandarización de los métodos que se usan en todos los dispositivos. 
En este laboratorio se pretende utilizar todos los conocimientos adquiridos hasta el momento para plantear y configurar una red pequeña para que los habitantes de una casa puedan acceder a internet desde dispositivos alámbricos e inalámbricos. Se hará una profundización en los equipos, las conexiones y los protocolos empleados para hacer posible el correcto funcionamiento de esta red. Asimismo, se realizará una profundización en el funcionamiento del servidor, pues fue el componente más complejo que se empleó.




# Desarrollo de la solución


## Equipos:


Para conseguir establecer la conexión de la red desde un servidor hasta un terminal de usuario personal utilizamos varios tipos de dispositivos de red:


> **Módem:** Para empezar, describiremos todos los dispositivos que componen la red local (LAN) en el laboratorio. La LAN empieza desde el módem, que es el dispositivo que se encarga de permitir que la red local se comunique con la red de área extensa (WAN), normalmente mediante un proveedor de internet. En este caso, y debido al limitado alcance del laboratorio, este está conectado a una nube que nos sirve de representación del internet.
>
> **Wireless Router:** Un router por sí solo se encarga de enrutar los paquetes de información en la red a sus respectivos destinos para segmentar de forma eficiente la información, y hacer que no toda la información que recibe el módem tenga que ser transmitida a todos los terminales del sistema. Además de esto, nótese que el router escogido en Packet Tracer tiene integrado un punto de acceso inalámbrico para la conexión de dispositivos como celulares o portátiles. El router tiene solo 4 puertos ethernet, que son suficientes para este laboratorio pero serían insuficientes en redes con más terminales, por lo que se usó un switch.
> En este caso, se usó el router como punto de acceso inalámbrico, por lo que vale notar que se configuró la red inalámbrica 2.4G para su uso en celulares y portátiles.
>
> **Switch:** El switch, a grandes rasgos, se encarga de convertir un solo puerto ethernet en el router en cuatro puertos diferentes. Por supuesto, el switch tiene la capacidad de segmentar la red para cada equipo conectado de forma que la información no es repetida en todos, sino que se dirige solo a su destino.
>
> **Cloud PT:** Packet Tracer nos ofrece la opción de utilizar la abstracción de *Cloud PT*, de ahora en adelante nube, para representar todas las tecnologías adicionales que no son ni ethernet ni seriales. En este caso, utilizamos la nube como una forma de transmitir la información entre el servidor y la LAN manteniendo la idea de que hay una WAN en medio. Así, la configuración de la nube requiere que, una vez conectados los terminales a usar, se especifiqué que terminales se quieren comunicar entre sí, por lo que comunicando el módem con el servidor se simula una red WAN.
>
> **Servidor:** Por último utilizamos un servidor para almacenar la información de la página. Puesto que su configuración es más complicada que el resto de dispositivos, lo explicaremos en detalle más adelante.


## Conexiones


Para el laboratorio usamos 3 tipos de conexiones:


>**-Copper Straight Through (Cobre cable de red directo):** Lo podemos ver en la conexión PC Mamá -> Swich y PC Papá -> Switch, esto se debe a que el mismo propósito del cable es conectar dos dispositivos diferentes ya que no necesitamos cruzar los canales. En el caso de necesitar cruzar los canales sería porque estamos buscando conectar dos dispositivos iguales (no se presenta el caso en el laboratorio), por los que los pines de salida no pueden ser los mismos de llegada. En este caso el cable directo mantiene los pines iguales entre los dos conectores.
>
>**-Cable coaxial:** Lo encontramos en la conexión del modem -> internet, este lo usamos ya que no se ve afectado por ◊interferencias externas, además de que logra trasmitir datos a largas distancias, este transmite la red de área extensa (WAN Wide Area Network).
>
>**-Wireless (Inalámbrico):** Esta conexión la vemos de los siguientes dispositivos smartphones -> router y laptop -> router, esta última necesitó de una modificación en uno de sus módulos ya que este por defecto viene con uno que solo funciona con un cable ethernet de cobre, así que lo cambiamos por un WPC300N, el cual funciona Wireless. Este funciona gracias al router, recibiendo frecuencias que viajan por el aire para llegar a los dispositivos, en el nuestro caso la red tenía autenticación, así que debíamos poner la contraseña para poder hacer uso de la red.


## Protocolos:


Como en toda red informática, en este laboratorio se utilizaron múltiples protocolos y métodos que permiten el correcto manejo de la información y regulan la comunicación de dispositivos. A continuación, mencionaremos los más relevantes.


> **-IPv4:** Probablemente el protocolo más importante de toda nuestra red, consiste en definir una serie de direcciones de 32 bits para la transmisión organizada de información a través de redes físicas. Actualmente, y debido al enorme crecimiento del Internet en los últimos tiempos, se ha desarrollado otro protocolo conocido como IPv6, que tiene un número de direcciones totales que superan por órdenes de magnitud a las que puede generar en total el IPv4, sin embargo, para la red propuesta en el laboratorio este protocolo es más que suficiente.
>
> **-DHCP:** Mediante este protocolo, un router es capaz de asignar a cada equipo dentro de su red LAN una IP única para su navegación por internet. Se realiza de manera automática y dinámica a todos los dispositivos que se conectan con la red y generan una solicitud, y aparte de dirección IP asigna gateways predeterminadas, máscaras de subred y otros parámetros de red.
>
> **-DNS:** Este protocolo se encarga de transformar un “nombre” o dirección de una página web al número IP bajo el que realmente está identificado ese dominio. Básicamente, permite relacionar IP’s con nombres para que nosotros los usuarios podamos memorizar solo los nombres y olvidar las IP’s, facilitando la navegación web.
>
> **-HTTP:** Este protocolo permite la transferencia de datos a través de archivos a través de la red. Básicamente, permite que la información de las páginas web montadas en servidores puedan ser accedidas desde la red mediante esquemas de petición-respuesta entre clientes y servidores.
>
> **-WPA2-PSK:** Uno de los muchos protocolos de seguridad informática. Como todo protocolo de seguridad, se encarga de establecer las claves que se utilizarán para cifrar la comunicación entre punto de acceso y el terminal del usuario. WPA2 es un protocolo que soluciona las vulnerabilidades tanto de su antecesor, el WPA, como del primer algoritmo de seguridad, el WEP. Utiliza un método de encriptación más sofisticado conocido como AES (Advanced Encryption Standard) que el TKIP, que venían utilizando sus antecesores. Esta versión en específico, notada por terminar en -PSK (Pre-Shared Key) tiene una clave precompartida en vez de una clave diferente para cada usuario como en su versión original, y la escogimos puesto que es la más cómoda para las redes de hogar en las que todos los miembros conocen la misma frase contraseña.


## Server:


El servidor funciona como un ordenador que siempre esta encendido, con el fin de guardar información, y darle esta información al cliente. En este caso buscamos albergar una pagina web muy simple basada en HTTP.
Usamos de varios servicios en el servidor, para que este funcione correctamente.
En el DHCP,  configuramos para que le otorgue una IP a los clientes, en este caso los dispositivos de la casa de Juanita.
En el server nosotros le damos la Getaway/DNS Ipv4, la cual será la dirección de nuestra página web, pero luego esta será cambiada en el servicio de DNS, donde le pondremos “cisco.com”, lo que ocurre es que el este servicio resuelve la dirección como la IP estática de la página web del servidor.


# Desafíos afrontados:


Para el desarrollo del laboratorio afrontamos ciertas limitantes, ya que cisco packet tracer no era estable durante el desarrollo de este, con esto nos referimos a que el software de simulación cuando terminamos todas las configuraciones no nos dejaba acceder a la página web, además de que los dispositivos móviles no se conectaba automáticamente, la forma de solucionarlo fue cerrar y volver a abrir el programa, con lo que descubrimos que en próximas ocasiones puede que solo sea caso de reiniciar el software.


Tambien tuvimos una limitante con base a la configuracion del server, ya que este tiene muchos servicios y hay muchas secciones de darle nosotros mismos datos, como la IP, estos son valores que nosotros no conocemos por lo que nos tocó basarnos en la introducción a las herramientas de Packet Tracer, y videos en internet. 


Por otra parte consideramos que el DHCP solo debía ser configurado localmente en el router de la casa, pero para que los dispositivos se conectarán con el servidor,  el servidor también tenía que proveer este servicio. Sin este no se podía acceder a la página web.


# Conclusiones:


El principal aporte que nos deja este laboratorio es, por supuesto, la capacidad de construir redes que desarrollamos gracias a él. Entender la teoría, en concreto el funcionamiento de ciertos dispositivos, la función de determinados protocolos o la situación en la que se deben usar ciertos cables, no es suficiente para ser un experto en redes de comunicación de datos, y es solo cuando tenemos que enfrentarnos a problemáticas reales con esos conocimientos que empezamos a construir relaciones entre ellos y apropiarnos de lo realmente importante.


Vale la pena mencionar que un acercamiento a este software de simulación fuera de las actividades guiadas que podemos encontrar en Skills for All también saca a relucir todas las ventajas y desventajas de trabajar con Packet Tracer. La práctica fuerza a familiarizarnos con la interfaz y a ser más eficientes en la búsqueda y configuración de dispositivos. Sin embargo, la más molesta y más importante de aprender, es que en ocasiones el problema puede no ser nuestro, y que simplemente reiniciar el programa solucionará el mal funcionamiento.


Por último, de este laboratorio pasamos de nuestra abstracción mental de lo que es una red de internet al verdadero entendimiento de la estructura y funcionamiento básico de una. Con las habilidades y entendimiento desarrollados en la práctica podemos comprender de mejor manera los detalles de cada proceso específico, y así será más fácil aprender acerca de más protocolos, procesos, dispositivos y funcionamientos en lo que nos queda de curso.






# Referencias:


-[1] Concepto. 2021. Protocolo Informático - Concepto, propiedades y ejemplos. [online] Available at: <https://concepto.de/protocolo-informatico/> [Accessed 9 August 2022].

-[2] De León Guerrero, E., 2016. Redes inalámbricas WPA/WPA2 ¿La protección ya no es suficiente? | Revista .Seguridad. [online] Revista.seguridad.unam.mx. Available at: <https://revista.seguridad.unam.mx/numero-19/redes-inalambricas-wpawpa2-la-proteccion-ya-no-es-suficiente> [Accessed 9 August 2022].

-[3] Calderon, C., Calderon, C. and Calderon, C., 2021. ¿Qué son los dispositivos de Red y para qué sirven?. [online] Redes de Computadores. Available at: <https://www.plotandesign.com/redes/dispositivos-de-red/> [Accessed 9 August 2022].

-[4] Sepúlveda, M., 2022. Armando un Servidor en Cisco Packet Tracer - eClassVirtual - Cursos Cisco en línea. [online] eClassVirtual - Cursos Cisco en línea. Available at: <https://eclassvirtual.com/armando-un-servidor-en-cisco-packet-tracer/> [Accessed 6 August 2022].

-[5] L. Peterson, and  B. Davie, Computer Network: a systems approach, 5ed. Burlington, USA: Elsevier, 2012, Ch 8. 

-[6] Walton, A., 2022. Cable Directo, Cable Cruzado y Cable Consola ¿Cuáles son las diferencias?. [online] CCNA. Available at: <https://ccnadesdecero.es/cable-directo-cruzado-y-consola-diferencias/> [Accessed 9 August 2022].

-[7]Configurar.pro. 2022. ▷ ¿Como Configurar Servidor Web Packet Tracer? 【 agosto 2022 】 Configurar.pro. [online] Available at: <https://configurar.pro/servidores/como-configurar-servidor-web-packet-tracer> [Accessed 9 August 2022].
