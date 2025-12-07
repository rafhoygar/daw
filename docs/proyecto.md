---
title: Instalación del servidor FTP en Debian y uso de Filezilla como cliente 
---

# Instalación de un servidor de FTP en Debian y un cliente en nuestro sistema anfitrión

## Descripción
En este proyecto se describe la instalación de un servidor FTP en el sistema operativo Debian 11 y su posterior configuración. Además, también se describe la instalación de FileZilla como cliente y su posterior configuración en nuestro sistema anfitrión. Finalmente, comprobamos el correcto funcionamiento del servidor y su conexión con nuestro sistema anfitrión.

## Pasos seguidos

1. **Instalación de un servidor de FTP en Debian 11**
   1.1. Actualizamos  el sistema
   1.2. Instalamos vsftpd (Very Secure FTP Daemon) en Debian 11
   1.3. Comprobamos su funcionamiento
   1.4. Configuramos el Cortafuegos NFTables para abrir el puerto 21
   1.5. Aplicamos las reglas guardadas en NFTables
   1.6. Comprobamos el funcionamiento de NFTables.services
   1.7. Configuramos vsftpd editando el archivo /etc/vsftpd.conf
   1.8. Reiniciamos el servicio vsftpd para aplicar los cambios
   1.9. Creamos un usuario FTP
   1.10. Debemos crear un subdirectorio en /home/usuarioFTP para evitar que vsftpd nos deniegue que el directorio sea escribible (causa: uso de chroot_local_user)
   1.11. Reiniciamos el servicio vsftpd para aplicar los cambios 
2. **Instalación del cliente FileZilla como cliente en nuestro sistema anfitrión**
   2.1. Instalamos FileZilla en nuestro sistema anfitrión (Windows 11)
   2.2. Nos conectamos al servidor utilizando la dirección IP del servidor, el nombre de usuario y la contraseña que hemos configurado (conexión FTP sin TLS)
   2.3. Comprobamos que NFTables solo permite conectarse al puerto 21 configurado
3. **Configuración de un servidor de FTPS sobre TLS**
   3.1. Generamos certificados por OpenSSL
   3.2. Configuramos vsftpd editando el archivo /etc/vsftpd.conf activando esta vez el uso de SSL
   3.3. Reiniciamos vsftpd para aplicar los cambios
   3.4. Configuramos la conexión FTPS en FileZilla para la posterior conexión entre el servidor y nuestro sistema anfitrión
   3.5. Configuramos NFTables y vsftpd para el uso de puertos pasivos y mostrar así la importancia del uso de estos puertos para un mayor control
   3.6. Reiniciamos vsftpd para aplicar los cambios
4. **Ejemplos para probar el correcto funcionamiento de la conexión**
   4.1. Creación de un directorio en el servidor desde FileZilla
   4.2. Enviar un archivo de texto desde el sistema anfitrión al servidor FTPS y viceversa
   4.3. Enviar un directorio desde el sistemma anfitrión al srvidor FTPS


## Sistemas operativos y herramientas usadas
1. Debian 11 en nuestro servidor
   - Uso de NFTables para establecer las reglas del Cortafuegos
   - Uso de vsftpd para implantar el FTP y FTPS
   - Uso del editor nano pata editar los archivos de configuración
1. Windows 11 en nuestro sistema anfitrión
   - Uso de FileZilla como cliente para la conexión con el servidor

