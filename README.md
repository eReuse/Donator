# Donator
======================================================
Donator v1.1  (Mayo, 2011)

http://sf.net/projects/donator-xsr
------------------------------------------------------


______________________
Documentación
======================
 
 Este LEEME sirve para la configuración y uso de Donator


______________________
Notas del Lanzamiento
======================

 Por favor, lea el fichero changelog.txt para una lista completa de
 características que están disponibles en esta versión, así como mejoras
 y soluciones a bugs. 


_____________________
Instalación
======================

 Archivo binario para Debian/Ubuntu
 ==================================

 El archivo binario viene totalmente configurado para poder ser utilizado con
 la plataforma de la "Xarxa de Suport a la Reutilització (XSR)".

 Para instalar el binario en Debian/Ubuntu se debe ejecutar el siguiente
 comando:

        dpkg -i donator-1.1.deb


 Archivo tar.gz
 ==============

 Este archivo se utilizará para poder utilizar donator con otras plataformas
 diferentes a la XSR. A continuación se explica como configurar donator para
 adecuarlo a otras plataformas.
 Una vez descargado el archivo tar.gz se descomprimirá en el directorio
 donde se quiere instalar la aplicación mediante el siguiente comando:

	tar -xzvf <PATH>/<ARCHIVO>.tar.gz

 que creará un directorio donator cuyo contenido será el siguiente:

   - donator
                |- bin
                |    |- donator
                |- etc
                     |- donator.cfg
                     |- menu_ca.properties
                     |- menu_en.properties
                     |- menu_es.properties
                     |- vga.txt

 Claves para encriptación
 ------------------------
 Para la encriptación de los ficheros XML se debe tener un par de claves
 pública/privada, para generarlas hay que seguir el siguiente proceso:

 1- Ejecutar el siguiente comando:

	gpg --gen-key

 2- Seleccionar la opción "DSA y RSA".

 3- Elegir el tamaño de clave deseado.

 4- Elegir la  validez de la clave.

 4- Confirmar y rellenar los datos de la entidad o persona.
 La clave se identificará por la dirección de correo electrónico, por lo que
 es importante recordarla. Por último introducir una contraseña, que será la
 que se utilizará para desencriptar los ficheros XML.

 Una vez finalizado el proceso se habrá creado el par de claves. La clave
 pública la incorporaremos al directorio etc del programa donator y se
 utilizará para el encriptado, mientras que la clave privada se dispondrá
 en el servidor que recibe los xml y que desencripta los mismos.

 Para conseguir la clave pública en un fichero que podamos adjuntar al
 software, ejecutaremos el siguiente comando:

	gpg --export <direccion_correo>@<dominio> > key.bin

 Copiaremos el fichero key.bin que acabamos de crear en el directio etc de
 la instalación de donator.

 Fichero donator.cfg
 -------------------
 Por último, se debe editar el fichero donator.cfg del directorio etc
 modificando los  parámetros adecuadamente para que se adapte a la nueva
 plataforma:

   * EMAIL=reutilitza@gmail.com
	Cambiar por la dirección de correo electrónico que se ha utilizado para
	crear el par de claves.

   * HOST_SFTP=xsr.org.es
	Cambiar por la IP o dirección del servidor de SFTP donde se enviarán
	los ficheros XML con la aplicación.

   * PORT_SFTP=donator
	Cambiar por el puerto donde escucha el servidor de SFTP.


______________________
Uso de la aplicación
======================

 Para arrancar la aplicación se debe ejecutar el fichero donator situado en el
 directorio bin de la instalación.

 El programa muestra una cabecera con el mensaje Donator y verifica los
 componentes del equipo, creando un fichero con toda la información recopilada.

 A continuación se muestra un formulario donde se pide al usuario ingresar el 
 nombre de usuario y contraseña de la web de la XSR.

 Finalmente se intenta subir el fichero al servidor para su posterior alta en 
 la web. Una vez finalizado el proceso se muestra la carpeta donde se encuentra
 el fichero creado (en caso de fallo de la alta, el usuario podrá dar de alta
 el equipo manualmente) y abriendo la web de la XSR en el navegador web.

______________________
Soporte
======================

 Cualquier problema con esta versión puede ser reportado en la siguiente
 dirección de correo electrónico:
 maxfer@gmail.com
