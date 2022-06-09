# BootCamp DevOps Engineer

Máquinas Virtuales en AZURE

Desafío 3 Azure - Desafío 1 Semana 1 
## Máquinas Virtuales en Azure
Alumno  Marcelo Piroddi 
Profesores Gino Rojo – Gastón Baravalle



# Inicio de sesion en Azure

## Paso 1
Nos dirigimos al portal de Azure ubicado en https://portal.azure.com ,  e iniciamos sesion.

## Paso 2
Escribimos en la seccion de busqueda ; “maquinas virtuales” , a partir de alli seleccionamos “Crear” y se abrira la pagina con los detalles para la creacion de una maquina virtual.

Si hemos procedido correctamente veremos una pagina con el texto “Crear de maquina virtual”, como la siguiente imagen


![image](https://user-images.githubusercontent.com/105083569/172958486-99fc764e-ede2-4500-ac17-4ac6e5c9f18f.png)


## Paso 3
Recién comenzamos, debemos seleccionar la suscripción indicada y a esta máquina virtual debemos darle nombre. Usaremos los detalles que nos informa la imagen para completar los espacios.

![image](https://user-images.githubusercontent.com/105083569/172958523-843e180c-18de-474b-9424-21190ef381d7.png)

## Paso 4
Completamos los detalles de instancia, guiándonos con los datos como aparecen en la imagen.

![image](https://user-images.githubusercontent.com/105083569/172958561-ed270b67-90f1-4189-b0f6-9e9a94687e3c.png)

## Paso 5

### En la sección cuenta de administrador darle un usuario y contraseña. Usamos los datos que aparecen en la imagen.

![image](https://user-images.githubusercontent.com/105083569/172958607-bda33ef3-6829-4741-aed0-65f5fc58d515.png)

## Pasó 6
Habilitamos en la sección “Reglas de Puerto”, los puertos RDP 3389 y HTTP 80.

![image](https://user-images.githubusercontent.com/105083569/172958629-26bd59db-1a4f-4055-8226-dd22a70a055e.png)

## Paso 7
A veces da error, volver a insistir. Refrescar la página es también una opción.

En el peor de los casos empezar de nuevo.

A veces Azure tiene estos problemas.

![image](https://user-images.githubusercontent.com/105083569/172958672-6fc60e73-d933-4353-8fe6-073562dc816f.png)

## Paso 8

Ya estamos pronto a finalizar, Máquina virtual creada

![image](https://user-images.githubusercontent.com/105083569/172958696-481311cd-eaa1-4ea9-afd1-20a031891777.png)

Se están implementando los cambios, paciencia

![image](https://user-images.githubusercontent.com/105083569/172958852-63be8e9a-228f-49a2-bb9c-91d108a6edbe.png)

Cambios implementados, listo.

![image](https://user-images.githubusercontent.com/105083569/172958862-153823b4-8a4f-4811-8cd1-c6bcd9b28c9e.png)

Una vez finalizada la implementación, seleccionamos “Ir al recurso”

Fin


#
#
#

# Ejercicio Conexión a la máquina virtual

Vamos a crear una conexión a Escritorio remoto en la máquina virtual,  lo que nos permitirá conectarnos a la máquina virtual desde un equipo  de Windows.

En la imagen siguiente seleccionamos Conectar RDP.

Y descargamos el archivo RDP

![image](https://user-images.githubusercontent.com/105083569/172958960-65654858-e304-4c55-90c5-0954839680f5.png)

el archivo RDP una vez descargado veremos la siguiente imagen;

![image](https://user-images.githubusercontent.com/105083569/172958973-13793b48-d49f-410d-a9f0-92284239cdcb.png)

Hacemos doble clic en el archivo y nos aparecerá esta ventana, damos “Conectar” y seguimos

Al abrir el archivo veremos “ Seguridad de Windows” en el margen superior izquierdo .

Seleccionamos “Más opciones”  y, después, “Usar otra cuenta”.  Allí escribimos  “Nombre de usuario” como localhostusername,  escribimos la contraseña que creamos para la máquina virtual y, luego, hacemos clic en Aceptar.

![image](https://user-images.githubusercontent.com/105083569/172959021-4ec0bafc-5e38-4434-98b0-fb5116b78da3.png)

Al conectarse podremos ver la siguiente imagen .
![image](https://user-images.githubusercontent.com/105083569/172959046-bf4f51b6-2936-49b0-aa8c-76c92d69621e.png)
#

![image](https://user-images.githubusercontent.com/105083569/172959058-bea7c605-b01a-4983-b83a-663de9bf7776.png)

Fin


#
#
#

# PAGINA PRINCIPAL DE  IIS


Vamos al portal de Azure, seleccionamos  la máquina virtual que creamos, en la información general de la máquina virtual,  mantenemos  el mouse sobre la dirección IP para mostrar el texto “Copiar al Portapapeles”.

Copiamos la dirección IP y la pegamos en una nueva pestaña de nuestro explorador.

Se abrirá la página de bienvenida de IIS predeterminada, y debería tener el siguiente aspecto .

Pero lamentablemente eso no paso.

Usamos dos exploradores diferentes, Google Chrome y Microsoft Edge, con resultado negativo.
![image](https://user-images.githubusercontent.com/105083569/172959207-3b744c7d-32ee-45f8-aa62-55334b7034d1.png)


Seguimos buscando soluciones, posible problema Windows no tenga activado la compatibilidad con “IIS 6”.

Vamos para allá  ➽ Panel de Control  ➽ Programas y Características ➽ Activar o desactivar las características de Windows ➽ Controlamos.

![image](https://user-images.githubusercontent.com/105083569/172959236-f2ac16e5-5781-4019-8deb-1ff251da7475.png)

Activamos las pestañas como se ven en la pantalla y veremos a continuación al aceptar .

![image](https://user-images.githubusercontent.com/105083569/172959252-955a9319-da64-4793-911f-bc224d97da1c.png)

Para controlar que este activado, escribimos en nuestro explorador “localhost” y deberíamos recibir como respuesta la siguiente imagen si esta todo correctamente realizado.

![image](https://user-images.githubusercontent.com/105083569/172959273-4731f7da-ce14-4c1f-83b0-d29b5ddf7ec9.png)

Probamos de nuevo
![image](https://user-images.githubusercontent.com/105083569/172959290-f2dd9260-34f9-4785-bcc6-3053d4ae052a.png)
Y el resultado sigue siendo negativo.

Buscamos otro camino, creamos una IP publica dentro de AZURE y se la añadimos a nuestra VM

![image](https://user-images.githubusercontent.com/105083569/172959312-812a5986-a190-4fed-945f-7440b5b6c8f6.png)

![image](https://user-images.githubusercontent.com/105083569/172959320-df8316ee-410d-4fb3-822c-d1139d3180b0.png)
Probamos haciendo PING desde CMD y negativo
![image](https://user-images.githubusercontent.com/105083569/172959335-11fb96a0-2625-4710-80ac-d53d609d0fcb.png)


Seguimo buscando soluciones.  Nos vamos a este blog, donde nos indica …
![image](https://user-images.githubusercontent.com/105083569/172959366-236a1b31-d8d4-4564-af24-05c71631d124.png)

Que si tenemos resultados negativos con el PING, podemos utilizar métodos alternativos, como usar la POWERSHELL con el comando “ Test-NetConnection”.
Probamos.
Resultado negativo.
Seguimos averiguando.

![image](https://user-images.githubusercontent.com/105083569/172959387-a91239d8-0c4c-4c8b-aa25-1b51bdb2324f.png)

Vemos de actualizar POWERSHELL y seguimos ,

![image](https://user-images.githubusercontent.com/105083569/172959408-07b05f09-abb1-4ef0-8073-d21031a47a62.png)

![image](https://user-images.githubusercontent.com/105083569/172959416-4b6261f2-1daa-4bab-a030-d2b6cdc3a169.png)

![image](https://user-images.githubusercontent.com/105083569/172959426-1c989e8d-e545-40dc-aa48-bf10828583f4.png)

Terminamos de instalarla y probamos
![image](https://user-images.githubusercontent.com/105083569/172959442-5e5df665-66fe-4402-bf20-58ed9f6b5064.png)

Resultado negativo, no reconoce el comando.

Seguimos buscando soluciones, otra posibilidad es hacer Ping con PSPing de Sysinternals Tools, es una de las herramientas incluidas en las PsTools .
Descargamos el archivo PSPing.exe y lo guardamos en Equipo , Disco local C, Windows, System32 , como muestra la imagen .
![image](https://user-images.githubusercontent.com/105083569/172959480-511a9299-d7ae-4229-9451-e78d7e7dbf32.png)

Ejecutamos CMD como administrador
![image](https://user-images.githubusercontent.com/105083569/172959510-da15d6be-3359-44a8-a95b-074f191c3130.png)

y probamos nuevamente, primero con un ping que conocemos ,

![image](https://user-images.githubusercontent.com/105083569/172959539-955141f1-ebd9-4af1-bdf6-aaccbefa59e7.png)


Y después con el de la VM, como podemos ver en la siguiente imagen

![image](https://user-images.githubusercontent.com/105083569/172959556-efa5cb7c-beb4-41b2-a019-71d7284601b4.png)

Y el resultado fue
![image](https://user-images.githubusercontent.com/105083569/172959578-8243621d-342e-41c5-b34e-eb8eb6c6e5a9.png)

Resultado negativo.

Seguimos investigando,  ampliaremos más adelante ya que esta última etapa del desafío nos está consumiendo demasiado tiempo en un error que no hemos podido resolver hasta ahora.

Hoy jueves temprano,  quisimos empezar en la mañana con pruebas para estar preparados y poder tener desplegada y lista una VM para la reunión con Gastón Baravalle,  para tratar de buscar soluciones al problema.  Lamentablemente eso no ocurrió,  recién a la tarde se nos habilito el patrocinio de parte de Microsoft gracias a la gentileza de Paola.

Jueves 22:30hs    -26.05.2022}

PS: Quedo en volver a probar más adelante y rever donde está el error, por ahora culmino aquí para no seguir retrasándome. 


#
#
#
#
#
Nos vemos en el [Dia 5](day05.md).
