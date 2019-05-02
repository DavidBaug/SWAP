Cloud Computing



##### Qué es

Cloud Computing es un paradigma que permite ofrecer servicios de computación a través de una red, que normalmente suele ser internet. Dicho paradigma surge por la necesidad de compartir los recursos de un sistema (ofrecer servicios) entre distintos usuarios concurrentemente.  Con el avance de la tecnología este paradigma se ha vuelto indispensable para el uso cotidiano de cualquier persona, ya que la inmensa mayoría de las empresas ofrece sus servicios en la nube. 

##### Servicios en la nube

Como hemos visto en esta asignatura, el tener un servicio alojado en la web nos permite escalar el sistema para poder ofrecer el servicio a más usuarios al mismo tiempo, ofrecer una respuesta más rápida ante  la resolución de un problema concreto.

Para tratar el tema escogeré varios tipos de servicios de cloud computing y de escritorio y compararemos lo que supondría ejecutarlos en una granja web en la nube o en el sistema del usuario. 

Base de datos
Suite de ofimática
Servicio de streaming de música
Editor de fotos
Videojuegos

##### Servicios en la nube ejecutados en el cliente

A pesar de que ejecutar una aplicación en la nube suela ser más rápido que ejecutar una aplicación en el sistema del usuario, la comunicación entre cliente y servidor está acotada por la latencia de red, lo que puede llegar a hacer que el diálogo con el servidor y la respuesta que ofrece sea más lenta que lo que se tardaría al ejecutar la aplicación en el cliente.

Debido a esto surge Javascript, un lenguaje de programación que permite ejecutar código y manejar información en el lado del cliente, sin necesidad de establecer una comunicación con el servidor para cada operación. 

Esto no sólo resuelve el problema que tenemos con el tiempo de respuesta, si no que al tratar con un sólo lenguaje que interpreta el navegador podemos implementar aplicaciones capaces de ser ejecutadas desde casi cualquier dispositivo.

Con el nacimiento de Javascript, varios desarrolladores ven su potencial y comienzan a importar sus aplicaciones a la web usando usando sus propias  modificaciones del lenguaje. Para evitar la incompatibilidad, el W3C (World Wide Web Consortium), diseña el estándar DOM (Document Object Model) con el que las partes de un documento HTML son objetos a los que JS puede acceder.

Desde que surgió Javascript se han creado varios lenguajes de programación web, aunque a día de hoy se ha convertido en uno de los más populares y usados por distintos desarrolladores.





##### Base de datos

¿Qué debemos pensar a la hora de decidir si ejecutar una Base de Datos en la nube o en el cliente? Almacenamiento principalmente, y no sólo secundario.

Cuando utilizamos un sistema en el que hagamos uso de una base de datos hacemos una serie de operaciones que el sistema debe resolver en memoria principal antes de escribir en disco. 

Sabiendo esto, ¿en qué casos no utilizarías cloud computing? En teoría nunca, es decir, siempre sería mejor utilizar cloud computing, ya que este tipo de aplicaciones, dependiendo del usuario, necesitará una capacidad de almacenamiento superior a la que ofrece un sistema convencional. Aunque puede quien piense que para almacenar el stock de una frutería no sea necesario utilizar cloud computing y baste con instalar un sistema sencillo en el ordenador personal. 

¿Qué problemas puede tener esto? Menos recursos, necesidad de mantener la consistencia de la base de datos, prevención ante la posible pérdida de datos por algún problema mediante uso de copias de seguridad y otros mecanismos...etc

Contratando un servicio en la nube no sólo aseguramos que la aplicación siempre sea rápida, si no que estamos previstos ante probables errores que puedan hacer que perdamos la información, que en algunos casos es incluso más "cara" que la infraestructura.

##### Suite de ofimática



### Introducción

Internet surge debido a la necesidad de compartir información de una forma distinta a la convencional. Gracias a esto se crea una red que permite conectar distintos puntos y realizar un intercambio de información, lo que combinado con el uso de servidores hace que cualquier usuario pueda recibir un servicio siempre que esté conectado a la red.

El uso de servidores se extendió con la finalidad de que cada usuario conectado a la red pudiera acceder a ese servicio. Dicha extensión hizo que infinidad de empresas ofrecieran todo tipo de servicios en la red, ya sea potencia de cálculo, capacidad de almacenamiento, información, aplicaciones web... etc.  

Dadas las capacidades de las granjas web, siempre será mejor que en caso de querer ejecutar una aplicación sea el servidor el encargado de hacerlo y ofrecer el resultado al cliente, aunque el tiempo de respuesta estará acotado por la latencia de red, lo que hace que en determinados casos sea más rápido ejecutar un programa en el cliente que en la web. Esto hace que aparezca Javascript, un lenguaje que permite que sea el cliente el que ejecute una aplicación en su ordenador, lo que hace que ahora el cuello de botella lo provoquen los recursos del sistema en vez de la latencia de red.

Con Javascript podemos ejecutar aplicaciones en el navegador, lo que en el caso de aplicaciones simples, como las de ofimática, podamos obtener un rendimiento similar al de una aplicación nativa. 



### Javascript

La creación de un lenguaje que interprete el navegador nos permite exportar las aplicaciones a cualquier dispositivo que disponga de un navegador capaz de ejecutar dicho código. Con su nacimiento, varios desarrolladores ven su potencial por lo que comienzan a importar sus aplicaciones a la web usando usando una modificación del lenguaje. Para evitar la incompatibilidad, el W3C (World Wide Web Consortium), diseña el estándar DOM (Document Object Model) con el que las partes de un documento HTML son objetos a los que JS puede acceder.  
