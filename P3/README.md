# Práctica 3: Balanceo de carga

## Índice

1. #### [Instalación nginx](#id1)

2. #### [Balanceo de carga](#id2)

3. #### [Configuración](#id3)

4. #### [Instalación haproxy](#id4)

5. #### [Configuración haproxy como balanceador](#id5)
6. ### [Comprobación funcionamiento](#id6)
7. ### [Ejemplo de balanceo con alta carga](#id7)


<div id='id1' />

### Instalación nginx

Lo primero que debemos hacer es actualizar el sistema para asegurar un mejor funcionamiento de la herramienta. Al intentar instalarlo puede que obtengamos este error.

![](./images/error_nginx.PNG)

Esto se debe a que estamos intentando instalar nginx mientras apache está activo, por lo que pararemos apache mediante *sudo service apache2 stop* y resolveremos el problema de instalación de nginx ejecutando lo siguiente *apt -f install*.

![](./images/arreglado_nginx.PNG)



Una vez instalado deberemos configurar el balanceador para hacer que la carga se reparta entre los servidores que tenemos activos. Para ello haremos uso de la directiva *upstream* para especifar la dirección de ambos servidores y crear un grupo sobre el que se repartirá la carga.

Para modificar la configuración de nginx accederemos al fichero */et/nginx/conf.d/default.conf* y lo modificaremos de la siguiente forma.