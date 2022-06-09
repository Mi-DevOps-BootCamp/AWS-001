# BootCamp DevOps Engineer	

## Sitio Estático en AWS 

04   Desafío 2 AWS – Semana 1 –

Sitio Estático en AWS
Alumno  Marcelo Piroddi  -  Profesores Gino Rojo – Gastón Baravalle

#
#
Accedemos a la consola de AWS y nos identificamos.

 Dentro de la consola buscamos el recurso S3.

![image](https://user-images.githubusercontent.com/105083569/172960337-8a959f91-be58-4d6b-9e4e-d6b81c606af1.png)

Creamos un nuevo bucket.

![image](https://user-images.githubusercontent.com/105083569/172960374-494cea71-079c-457f-8976-0b499723c1e3.png)

Le damos un nombre único y dejamos la región por defecto.

![image](https://user-images.githubusercontent.com/105083569/172960389-da26ab56-72cd-4bae-ba7d-ba17c2606538.png)

Un sitio web es accesible por cualquier usuario por lo que debemos permitir el acceso público a nuestro bucket. Desmarcamos el bloqueo del acceso público y podemos dejar el resto de la configuración por defecto.

![image](https://user-images.githubusercontent.com/105083569/172960416-4250846a-d29b-45a5-a196-a74a0a7af4ba.png)

Listo, esta creado.

![image](https://user-images.githubusercontent.com/105083569/172960436-bad0d7ee-9fee-4683-b1a4-b80ace9ba2e9.png)

Veremos esta pantalla al estar listo

![image](https://user-images.githubusercontent.com/105083569/172960467-a03345e0-76ad-4a7b-b186-228c7c052b8c.png)

Los bucket no tienen herencia, por lo que permitir el acceso público al bucket no implica que sus objetos tengan acceso público. 

Debemos crear una política, que permita el acceso a los objetos, y asociarlo al bucket

![image](https://user-images.githubusercontent.com/105083569/172960489-0f9f5ef3-a068-4d01-8f1e-2e6d998e95cd.png)

Para ello, en la sección Permisos buscamos el apartado Política de bucket y le damos a Editar

![image](https://user-images.githubusercontent.com/105083569/172960523-a8ca80d5-2d19-4760-9d1b-a82cdbcd5531.png)

Copiamos el ARN del bucket (nos servirá para el siguiente paso) y le damos Generador de políticas.

![image](https://user-images.githubusercontent.com/105083569/172960536-2f009528-735d-4c83-b991-aab84a36b194.png)

Aquí se nos abrirá la siguiente pantalla

![image](https://user-images.githubusercontent.com/105083569/172960557-010c6502-f3e6-427a-a4ba-3c9806e31c08.png)

Como tipo de política seleccionamos S3 Bucket Policy.

![image](https://user-images.githubusercontent.com/105083569/172960596-c21a0a81-8e30-4960-9366-609829249e53.png)

En Statement, rellenamos el campo Principal con un asterisco y seleccionamos GetObject como action.	

![image](https://user-images.githubusercontent.com/105083569/172960626-47a5ed1c-4c0c-4258-b86b-36e68f2c33c9.png)

Le damos a Add Statement,

 y después de ver el resumen del statement le damos a Generate Policy.
 
 ![image](https://user-images.githubusercontent.com/105083569/172960665-1c6b3789-986c-43cb-9397-9b24c433438b.png)

Se nos abrirá una ventana con el JSON de la política, la copiamos y volvemos a la pantalla anterior 

![image](https://user-images.githubusercontent.com/105083569/172960698-f3095196-2ede-453d-b22c-382963d7e524.png)

Pegamos el JSON de la política y lo guardamos.
(ver HOJA 10 )

![image](https://user-images.githubusercontent.com/105083569/172960715-6e8aa032-6888-496c-a2ac-630f8eabfd38.png)

Al finalizar veremos la confirmación

![image](https://user-images.githubusercontent.com/105083569/172960734-af6f1f2b-95b5-4888-b85f-c519a10209cb.png)

Una vez configurado los permisos, procedemos a subir nuestros ficheros. 

Podemos arrastrar los ficheros a la zona del bucket o usar el botón cargar y seleccionar los ficheros.

Le damos a cargar y volvemos al bucket.

![image](https://user-images.githubusercontent.com/105083569/172960763-2e1cbe03-0a1c-4efa-8ee6-93cd70a07d40.png)

Una vez configurado los permisos, procedemos a subir nuestros ficheros. Podemos arrastrar los ficheros a la zona del bucket o usar el botón cargar y seleccionar los ficheros. Le damos a cargar y volvemos al bucket.

![image](https://user-images.githubusercontent.com/105083569/172960796-81c4773f-2431-4ccc-a27c-317355966c63.png)

Para alojar nuestro sitio web deberemos buscar en la sección Propiedades el apartado Alojamiento de sitios web estáticos y darle a Editar.

![image](https://user-images.githubusercontent.com/105083569/172960818-0dbfd934-dd26-4533-a07a-62f982573fa6.png)

Habilitamos el alojamiento, indicamos el nombre del documento que queremos que funcione como índice, y también indicamos el nombre de la página de error si la tuviéramos en el bucket.

![image](https://user-images.githubusercontent.com/105083569/172960862-7023c97d-996a-4bd0-b26a-908ae2652ff3.png)

Guardamos los cambios y si volvemos a la sección Propiedades en el apartado Alojamiento veremos la dirección de nuestro sitio web en ACCION.

![image](https://user-images.githubusercontent.com/105083569/172960887-bc25f58d-711e-4f54-a83c-b3cd608285d5.png)

Si queremos mostrar una página en caso de producirse un error indicaríamos el nombre del fichero del bucket en Documento de error.  
#
En este caso use la imagen de Netflix para gestionar el código de ERROR .
![image](https://user-images.githubusercontent.com/105083569/172960929-f4414320-ed69-4ecd-b157-a1b1fe8afa90.png)


#
#
Para concluir eliminamos lo creado (nos cuidamos de generar gastos) 

![image](https://user-images.githubusercontent.com/105083569/172960952-827f025f-ba7b-4deb-9e31-ea6b6b322cdc.png)

Antes que nada vaciamos el BUCKET

![image](https://user-images.githubusercontent.com/105083569/172961007-beff12c7-a0e4-4b4c-82cc-164b994415c7.png)

Y lo eliminamos

![image](https://user-images.githubusercontent.com/105083569/172961021-8d50a2a9-ce67-4deb-b25f-083c34eeb162.png)

Pantalla de confirmación de eliminación

![image](https://user-images.githubusercontent.com/105083569/172961045-07039e0d-9431-439d-a43b-16d16c3203a2.png)


Fin



#
#
#
#
#
No vemos en el [Dia 6](day06.md). 
