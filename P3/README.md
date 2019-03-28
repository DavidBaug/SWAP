# Práctica 3: Balanceo de carga

## Índice

1. ### [Instalación nginx](#id1)
2. ### [Configuración](#id2)
3. ### [Balanceo de carga](#id3)
4. ### [Instalación haproxy](#id4)
5. ### [Configuración haproxy como balanceador](#id5)
6. ### [Comprobación funcionamiento](#id6)
7. ### [Ejemplo de balanceo con alta carga](#id7)


<div id='id1' />

## Instalación nginx

Para esta práctica habremos creado un balanceador de carga que nos permitirá distribuir la carga de trabajo entre los servidores de la granja. Para ello crearemos una máquina virtual en la que instalaremos el software para balancear. Las imágenes que aparecen a continuación son de una máquina clonada, pero al realizar el mismo proceso desde una máquina virtual nueva no he obtenido ningún error. Al crear una máquina nueva debemos realizar el mismo proceso que con las máquinas anteriores y configurar la red y las *keys* para el acceso remoto. En mi caso para el balanceador he usado la dirección **192.168.56.20**.

Lo primero que debemos hacer es actualizar el sistema para asegurar un mejor funcionamiento de la herramienta. Al intentar instalarlo puede que obtengamos este error.

![](./images/error_nginx.PNG)

Esto se debe a que estamos intentando instalar nginx mientras apache está activo, por lo que pararemos apache mediante *sudo service apache2 stop* y resolveremos el problema de instalación de nginx ejecutando lo siguiente *apt -f install*.

![](./images/arreglado_nginx.PNG)

<div id='id2' />

## Configuración

Una vez instalado deberemos configurar el balanceador para hacer que la carga se reparta entre los servidores que tenemos activos. Para ello haremos uso de la directiva *upstream* para especifar la dirección de ambos servidores y crear un grupo sobre el que se repartirá la carga. Y después especificaremos las características del servidor.

Para modificar la configuración de nginx accederemos al fichero */et/nginx/conf.d/default.conf* y lo modificaremos de la siguiente forma.

![](./images/nginx_conf.PNG)



Tras crear la configuración hacemos sudo *service nginx restart* para que se vuelva a iniciar con la configuración que acabamos de crear y al hacer *curl* a la dirección del balanceador deberíamos obtener lo siguie3te.


<div id='id3' />


## Balanceo de carga


![](./images/nginx_funciona.PNG)



Como se puede ver, al realizar una petición al balanceador este va distribuyendo el trabajo a los distintos nodos.

<div id='id4' />

## Instalación haproxy