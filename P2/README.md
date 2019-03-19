# Práctica 2: Clonar información entre servidores

## Índice

1. #### [Ejecutar comandos remotamente](#id1)

2. #### [Sincronización de archivos con rsync](#id2)

3. #### [Gestión de claves para conexión ssh](#id3)

4. #### [Estado servidor](#id4)

5. #### [CURL](#id5)

6. #### [SSH](#id6)


<div id='id1' />

### Ejecutar comandos remotamente

En este primer apartado suponemos el caso de que un servidor no disponga de espacio en el disco local para crear un fichero *tar.gz*, para solucionar esto usaremos *ssh* para crear el fichero en el equipo destino.

![](./images/tgz1.PNG)

Crearemos un directorio con varios archivos de prueba dentro para comprobar que funciona.

![](./images/tgz2.PNG)

Como podemos comprobar, al realizar la compresión y conectarnos a la segunda máquina mediante *ssh* especificamos la ruta y el nombre. Al irnos a la segunda máquina podemos ver que se ha creado en la ruta especificada el fichero con la compresión. Si descomprimimos y ejecutamos *tree* se aprecia que contamos con la misma estructura en ambas máquinas. 



<div id='id2' />

### Sincronización de archivos con rsync

En el caso anterior hemos compartido un directorio que comprimimos, pero también podemos compartir directorios y mantener una sincronización, tal como hace Google Drive, Dropbox, Mega... etc. Para ello descargamos rsync y ejecutamos el siguiente comando. En él, especificamos la máquina y el usuario al que nos conectamos, la ruta del fichero o directorio que queremos sincronizar y el nombre que tendrá en nuestra máquina.

![](./images/rsync.PNG)

Para este caso creo otro directorio en la máquina 1 y ejecuto *rsync* desde la máquina 2 y se puede comprobar que se crea el nuevo directorio y se copian todos los archivos del directorio especificado.

 

<div id='id3' />

### Configuración de Red en Servidor

Una vez conocemos la IP de nuestro host debemos crear una red en nuestra máquina con una IP estática para facilitar la conexión a ella. Para ello creamos una nueva interfaz en la que establecemos una IP estática dentro de la subred de nuestro host, es decir, si nuestro host tiene la dirección 192.168.56.1 debemos encontrar una dirección libre dentro de 192.168.56.X. En mi caso creo las siguientes interfaces.

![](./images/configuracion_red_2.PNG)





Una vez creadas podemos reinicar todo para comprobar que son válidas.

![](./images/configuracion_red_1.PNG)


<div id='id4' />

### Estado servidor

Durante la instalación de Ubuntu Server hemos instalado LAMP y PostgreSQL como gestor de base de datos. Vamos a comprobar que están en funcionamiento.

![](./images/apache.PNG)

Comprobamos el estado de apache haciendo *systemctl status apache2* y vemos que el proceso está activo.

![](./images/php.PNG)

Para probar que PHP está instalado podemos usar *php -v* o comprobar que existe el siguiente directorio.

![](./images/php2.PNG)

Y por último vamos a acceder al gestor de base de datos por defecto desde el modo root y al gestor que seleccionamos al instalar el sistema, PostgreSQL. Para entrar a mysql pasaremos a la cuenta root y entraremos usando su contraseña.

![](./images/sql.PNG)

En caso de entrar a PostgreSQL cambiaremos el usuario a  '*postgres*' y nos conectaremos con el gestor haciendo uso del comando *psql* y una vez dentro cambiaremos la contraseña para que el acceso sea más sencillo y no tener que recordar demasiadas contraseñas, aunque obviamente esto no es una buena práctica.

![](./images/psql.PNG)



<div id='id5' />

### CURL

Una vez hemos creado y configurado las interfaces de las dos máquinas podemos crear un fichero de prueba HTML para probar si podemos establecer conexión de una máquina a la otra.

![](./images/curl.PNG)

En la primera máquina creamos un fichero de prueba en el directorio */var/www/html* y en la segunda máquina hacemos una petición de ese archivo poniendo la dirección de la primera máquina. Como podemos comprobar la segunda máquina realiza la petición y recibe el archivo.


<div id='id6' />

### SSH

Sabiendo ya que las máquinas se ven podemos usar SSH para probar la conexión remota.

![](./images/ssh.PNG)

Al hacer SSH en la segunda máquina especificamos el usuario al que nos queremos conectar en la primera máquina y la dirección del host al que establecemos la conexión, ponemos la contraseña de ese usuario y al hacer *whoami* se ve claramente que estamos trabajando remotamente en la primera máquina como el usuario *ubuserver1*.