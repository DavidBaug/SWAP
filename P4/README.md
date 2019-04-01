# Práctica 4: Asegurar la granja web

## Índice

1. ### [Instalación certificado SSL](#id1)

2. ### [Configuración del cortafuegos](#id2)


<div id='id1' />

## Instalación certificado SSL

Los certificados nos permiten asegurar que la conexión que mantienen los clientes con el servidores es segura, de esta forma hacemos saber a los usuarios que pueden registrar sus datos personales con certeza de que no va a ocurrir nada malo.

En esta práctica veremos como instalar un certificado **SSL** (*Secure Sockets Layer*), aunque la versión actual no cumple con los estándares y se considera insegura. Al ser una práctica de clase instalaremos un certificado auto-firmado usando la herramienta *openssl*.



Una vez hemos instalado el certificado SSL deberemos copiarlo a las otras máquinas. Para esto he usado SFTP para conectarme remotamente desde la máquina en la que hemos creado el certificado a las otras máquinas en las que copiaremos los archivos. Debemos tener en cuenta que debemos darle permisos al usuario para que pueda modificar el directorio */etc/apache2/ssl/* para que podamos transferir los archivos sin ningún error.

Al igual que en la primera máquina, una vez hemos cargado los archivos debemos activar el SSL y recargar apache.

