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













































#
#
#
#
#
Nos vemos en el [Dia 5](day05.md).
