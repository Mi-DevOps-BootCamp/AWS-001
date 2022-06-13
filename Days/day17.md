

# Crear 1 VM con VirtualBox
#
# Objetivos  


En el siguiente ejercicio vamos a crear una máquina virtual con el virtualizador VirtualBox. 

Una vez creada vamos a instalar el servidor web Apache y accederemos a la publicación por defecto.

## ¿Qué recibimos?

El enlace a la imagen .ISO del sistema operativo a instalar —el VirtualBox ya debe estar instalado en nuestro ordenador—.

#
#

### Instrucciones

Ejercicio 1

De forma individual ejecutamos los siguientes pasos: 

****1)**** Descargamos el siguiente archivo (son 337 MB): https://www.debian.org/distrib/netinst 

Hacemos clic en la versión AMD64:

![Screenshot_21](https://user-images.githubusercontent.com/96561825/173422138-01751547-bc46-4e32-9eda-df8b021e27ff.png)


#

****2)**** Iniciamos VirtualBox. 

Allí vamos a crear una nueva máquina con la opción “Nueva”. En cada pantalla deberemos indicarle las siguientes opciones:
* Nombre: DebianCliente
* Sistema operativo: Linux 64 bit
* Memoria: 1024MB
* Disco Duro: Crear Disco Duro, 8 GB
* Tipo VDI, Reservado Dinámicamente

Nos debe quedar algo similar a esto:

![Screenshot_22](https://user-images.githubusercontent.com/96561825/173422283-6b84b64e-5f14-4866-af39-d30e0ac13327.png)


#
#

****3)**** Adicionalmente vamos a tener que modificar algunas opciones de nuestra VM, las cuales detallamos a continuación:


a)El tipo de red, que está como “NAT”, debemos cambiarlo a “Adaptador puente (Bridge)”, de la siguiente manera:
 
 
![Screenshot_23](https://user-images.githubusercontent.com/96561825/173422357-1c67ff64-c181-40e7-b3e8-7f6f080bee85.png)
 
Cuando hacemos este cambio, debemos elegir del listado la placa de red por la cual nos conectamos a Internet habitualmente.

![Screenshot_24](https://user-images.githubusercontent.com/96561825/173422524-dbdffddf-5fa9-475a-9eca-90ffa9fb7ea8.png)


b)Debemos vincular el archivo descargado a nuestra VM para que podamos instalarlo. Seleccionamos la opción “Almacenamiento”

![Screenshot_25](https://user-images.githubusercontent.com/96561825/173422588-9df1c732-5e21-4b54-9841-71ee68da4669.png)


Dentro de “Controlador IDE”, nos posicionamos sobre “Vacío” y en la parte de atributos hacemos clic en el ícono de CD y elegimos “Seleccionar un archivo de disco”. 
Allí se nos abrirá un explorador de archivos y debemos ir a nuestro archivo .ISO descargado.

![Screenshot_26](https://user-images.githubusercontent.com/96561825/173422741-0e252ac3-6fbb-417a-926b-93773ace0d0d.png)

Debería quedar así:

![Screenshot_27](https://user-images.githubusercontent.com/96561825/173422814-0c090bc1-0cc9-4d32-956e-f0df77ea9ede.png)

#
#

****4)**** Ahora vamos a iniciar nuestra VM desde el menú principal. Debe abrirse una ventana similar a la siguiente:

![Screenshot_28](https://user-images.githubusercontent.com/96561825/173422857-d196c961-1760-4d02-b7bd-c472200e82e8.png)

#
#

****5)**** Las opciones recomendadas para instalar el SO son las siguientes:

****Tip: Siempre observar qué tecla se asigna como “anfitrión”. En el caso de Windows por defecto es “CTRL DERECHA”. Esta tecla nos permite salir de la máquina virtual y que el cursor/puntero vuelva al sistema operativo host.****


a) Install, idioma Spanish y la distribución de teclado que manejemos.

b) En el nombre de la máquina, colocamos “debiancliente”, sin nombre de dominio.

c) Colocamos una clave al superusuario. Es importante que no la olvidemos.

d) Luego crearemos un usuario con el nombre que queramos. También nos pedirá clave y confirmación.

e) En el método de particionado de disco, seleccionamos “guiado - utilizar todo el disco” y elegimos el único disco en la lista. En la opción siguiente, le indicamos que como esquema de particionado vamos a colocar “Todos los ficheros en una partición”. Finalmente le indicamos “Finalizar particionado y escribir cambios en el disco”.

f) El proceso de instalación comenzará, es vital tener conectividad de Internet porque se descargan paquetes adicionales. En un momento se nos preguntará por el país de réplica, seleccionamos nuestro país de residencia

g) Debemos llegar a un menú de selección de programas, ahí podemos elegir entre usar interfaz gráfica o solo texto, nuestra idea es utilizar esta última. Para ello, debemos desmarcar la opción de “Entorno de escritorio Debian”. Debería quedarnos así:

![Screenshot_29](https://user-images.githubusercontent.com/96561825/173422925-ef714538-c363-4b5c-b396-e4fbe9dd317a.png)

h)Después de unos minutos, le indicamos que queremos instalar GRUB y seleccionamos el único dispositivo en la lista —normalmente /dev/sda—. Luego de esto el proceso nos pedirá reiniciar y, finalmente, se iniciará el SO. Deberíamos llegar a la siguiente pantalla:

![Screenshot_30](https://user-images.githubusercontent.com/96561825/173422995-eca53f2c-9bdc-4369-b473-68363227b5de.png)


i) Como login utilizaremos nuestro nombre de usuario y contraseña. Podemos también usar como usuario “root” y la contraseña de superusuario asignada.


#
#
****6)**** Ahora procederemos a instalar el servidor Web Apache, para ello, ejecutaremos las siguientes sentencias:

En caso de estar logueados como el usuario creado, debemos cambiar a root para poder tener permisos de instalación.

![Screenshot_31](https://user-images.githubusercontent.com/96561825/173423136-bddee2b9-e1d0-48ac-b435-970d346c112e.png)

En caso de estar logueados como root:

![Screenshot_32](https://user-images.githubusercontent.com/96561825/173423152-9ebdaac8-c932-4cec-8454-11834ab6b753.png)


Para poder probar que nuestro servidor web está instalado y corriendo, debemos averiguar la IP de nuestra VM, ejecutando la sentencia:

![Screenshot_33](https://user-images.githubusercontent.com/96561825/173423168-fe6bcebe-d750-42fb-a0ee-f2ba6d53ee16.png)

Esta nos devolverá una lista de los adaptadores de red que tenemos en nuestro sistema, sus direcciones IP y MAC address. La de nuestro interés es la 2, para este ejemplo es la 192.168.0.74.

![Screenshot_34](https://user-images.githubusercontent.com/96561825/173423206-065cf56a-b67a-4275-b24c-9536386f2012.png)


Con esta dirección, en nuestro equipo, abrimos en el navegador de Internet nuestra dirección IP (siguiendo nuestro ejemplo sería: http://192.168.0.74). Allí debemos obtener la pantalla de inicio de Apache.

![Screenshot_35](https://user-images.githubusercontent.com/96561825/173423252-dff3177a-433c-44c5-ae8d-113b08864073.png)


#
#

## Ejercicio 2

De forma individual ejecutamos los siguientes pasos:

Sin cerrar nuestra máquina virtual, lo que vamos a hacer es conectarnos vía SSH a la máquina virtual. Para ello, prepararemos nuestro entorno de trabajo con dos pasos previos:

* Habilitaremos el servidor SSH en nuestra VM, ejecutando las siguientes instrucciones:
En caso de estar logueados como el usuario creado, debemos cambiar a root para poder tener permisos de instalación:

![Screenshot_36](https://user-images.githubusercontent.com/96561825/173423431-024aebd8-fdf5-43bd-ba7b-c30f2c95f92e.png)

En caso de estar logueados como root:

![Screenshot_37](https://user-images.githubusercontent.com/96561825/173423422-f7bc7a0a-77c4-402b-9103-00eb18aec665.png)

* Descargamos la utilidad PuTTY desde el siguiente enlace y la instalamos:

https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
![Screenshot_38](https://user-images.githubusercontent.com/96561825/173423415-09c9464f-680a-4c31-b3dc-e735c3b7f38b.png)


****1)**** Abrimos la utilidad PuTTY.

![Screenshot_39](https://user-images.githubusercontent.com/96561825/173423522-c95a25b8-1473-46c4-a93e-ab7bdc11fd69.png)

Esta nos va a permitir conectarnos a nuestra VM. Este método de conexión es válido tanto para nuestra VM como para cualquier equipo que esté ejecutando Linux y tenga habilitado el openssh-server.

![Screenshot_40](https://user-images.githubusercontent.com/96561825/173423555-76fcc9ef-0983-4078-9ccd-cd2bdb32d6ae.png)

En “Host Name”, debemos colocar la IP de nuestra VM y hacemos clic en “Open”.

Allí nos vamos a encontrar nuevamente con la pantalla de logueo y lo haremos con nuestro usuario (en principio, no podremos hacerlo con el usuario root).

![Screenshot_41](https://user-images.githubusercontent.com/96561825/173423613-aa82d5cf-253a-47c5-9f9f-73263ab626ef.png)

Con toda la mesa de trabajo debatan sobre las siguientes preguntas y contesten en conjunto:

* Tanto para el ejercicio 1 como para el ejercicio 2, describan con sus palabras lo que acaban de hacer.
* Describir para qué sirve “apt-get”.
* Describir para qué sirve “su”.
* En el caso del ejercicio 1, ¿cuál fue la utilidad de instalar el paquete apache2? 
* En el caso del ejercicio 2, ¿les resultó familiar esta forma de conectarse a un equipo?








#
#
#
#
#
Seguimos en el [Día 18](day18.md)
