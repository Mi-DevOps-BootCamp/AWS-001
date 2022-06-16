

# CASO DE ESTUDIO: JIGSAW
#
## Grupo 4
#

### R a f a e l A v il a /Mauro Bazán / Nicolás Carabelli / Diego Luna / Marcelo Piroddi / Daniel Silva / Yevheniy Slyzkoukh
#
#### Bootcamps DevOps 2022 - Educación IT -  Docentes : Gino Rojo - Gaston Baravalle
#
#

### METODOLOGÍA DE TRABAJO

Análisis dinámico y estático de malware activo y real en un entorno seguro en Windows 7 mediante una máquina virtual con VirtualBox, utilizando la Suite Sysinternals y en Any Run mediante una sandbox.


### ENTORNO DE TRABAJO


● Maquina Virtual con Windows 7 64 bits operando en Oracle VM VirtualBox 6.1.32.

● Redes deshabilitadas, sin conexión exterior.

#
#
![Screenshot_6](https://user-images.githubusercontent.com/96561825/173985701-f47d63a9-e936-4198-91d1-1651a495dbdf.png)
#
#
![Screenshot_7](https://user-images.githubusercontent.com/96561825/173985666-068c0f6b-74e5-436c-92f6-9c4719998d94.png)
#
#
![Screenshot_8](https://user-images.githubusercontent.com/96561825/173985680-634b94f4-da8e-479e-bd74-088557faab3d.png)
#
#
![Screenshot_9](https://user-images.githubusercontent.com/96561825/173985687-b8d88473-bafc-4487-a47f-6d4b7b253d3b.png)
#
#



## ANALIZANDO CON PROCESS EXPLORER

### Administrador de tareas gratuito y monitor de sistemas Windows.


#
#
![Screenshot_10](https://user-images.githubusercontent.com/96561825/173985856-74835d7b-5c86-4758-91ea-a65c7d288182.png)
#
#
![Screenshot_11](https://user-images.githubusercontent.com/96561825/173985850-406aba94-eb6f-4b06-b441-1aa41fd3c3c7.png)
#
#
![Screenshot_12](https://user-images.githubusercontent.com/96561825/173985840-caa6ced0-e1f7-415f-b1da-ba2a40ea975a.png)
#
#
![Screenshot_13](https://user-images.githubusercontent.com/96561825/173985834-35534839-d34d-4b1e-8d05-e45314b4170d.png)
#
#
## ANALIZANDO CON AUTORUNS


### Herramienta que permite mostrar los programas, servicios y drivers al momento de encender la computadora.

#
#
![Screenshot_14](https://user-images.githubusercontent.com/96561825/173986067-d6f84d53-d6f8-4812-ba2a-157de7d14da7.png)
#
#

![Screenshot_15](https://user-images.githubusercontent.com/96561825/173986063-9dc41276-af7f-429f-b935-205e202561a4.png)
#
#

![Screenshot_16](https://user-images.githubusercontent.com/96561825/173986058-165be3c3-74c1-46cc-bc35-894e19fd16f2.png)
#
#
![Screenshot_17](https://user-images.githubusercontent.com/96561825/173986052-826de7f2-6b64-4750-a6fc-47ed26028de2.png)
#
#

![Screenshot_18](https://user-images.githubusercontent.com/96561825/173986046-6aaa2e9d-f34c-42a0-ae1a-e48ee67b3b4f.png)
#
#
![Screenshot_19](https://user-images.githubusercontent.com/96561825/173986042-b3413cfa-a747-4f14-acd3-eb6852a05679.png)
#
#


## ANALIZANDO CON AUTORUNS}

### Herramienta que permite mostrar los programas, servicios y drivers al momento de encender la computadora.


#
#
![Screenshot_20](https://user-images.githubusercontent.com/96561825/173986296-d1f02a0a-f43c-4176-b2ad-b90490f7f437.png)
#
#

![Screenshot_21](https://user-images.githubusercontent.com/96561825/173986286-5afb4050-aa44-4a9d-9577-ed5d148bcd05.png)
#
#
![Screenshot_22](https://user-images.githubusercontent.com/96561825/173986276-380577f1-5479-407a-9661-bc708673c3cf.png)
#
#
![Screenshot_23](https://user-images.githubusercontent.com/96561825/173986269-d6ce97b0-ffe5-4e32-941b-cef6f25add1c.png)
#
#



## UTILIZANDO ANY.RUN

### Servicio Web que permite el análisis de malware dentro de una sandbox. 

### Incluyendo MITRE ATT&CK

#
#
![Screenshot_24](https://user-images.githubusercontent.com/96561825/173986794-f1f15286-dba2-483f-bd2b-a9b87d037a1e.png)
#
#
![Screenshot_25](https://user-images.githubusercontent.com/96561825/173986788-5937b24c-796a-437e-83f9-90c78550bbc8.png)
#
#

![Screenshot_26](https://user-images.githubusercontent.com/96561825/173986783-0a43f00a-2f22-4fd8-9387-d2ce6fde7bee.png)
#
#
![Screenshot_27](https://user-images.githubusercontent.com/96561825/173986767-4649b73e-80dc-4a0e-b7b9-7f253f93b3e3.png)
#
#
![Screenshot_28](https://user-images.githubusercontent.com/96561825/173986758-e0f0cf20-6e45-4a8c-8cc5-ab5d74f180df.png)
#
#
![Screenshot_29](https://user-images.githubusercontent.com/96561825/173986751-eb195d2f-5108-4547-a331-f1edc68a4615.png)
#
#
![Screenshot_30](https://user-images.githubusercontent.com/96561825/173986747-a193547f-5978-4d43-b699-d1705caed261.png)
#
#

![Screenshot_31](https://user-images.githubusercontent.com/96561825/173986745-cdc8ccb7-43a7-49ca-9a27-410e341e8d78.png)

#
#

### CONCLUSIONES
#

● Utilizando la Suite Sysinternal de Microsoft, se nos permite identificar el comportamiento del Ransomware

● Contar con un entorno controlado es esencial, ya que limitamos el daño del Ransomware y nos permite comprender su comportamiento dentro del SO.

● Al utilizar ANY.RUN + Mitre Att&ack obtenemos un informe por escrito con todos los detalles del ataque.

A su vez ayudamos a la comunidad a poder estudiar formas más efectivas de protección, aprendiendo del comportamiento de las amenazas.

● Encripta archivos personales y elimina pide pago.

● Edita el registro del SO para tener persistencia.

● Crea un proceso de nombre conocido pero sin firma.

● Modifica archivos en la carpeta de extensiones de Chrome.

● Roba credenciales del navegador Web


#
#

FUENTES: 

https://drive.google.com/file/d/1DBFGp2OIFE0EzL5shf-_fA0at0hXp6kL/view?usp=sharing

https://docs.microsoft.com/en-us/sysinternals/downloads/

https://github.com/ytisf/theZoo/blob/master/malware/Binaries/Ransomware.Jigsaw/Ransomware.Jigsaw.zip

https://www.virtualbox.org/

https://any.run/


Libro : Troubleshooting with the windows sysinternals tools 2nd edition ; CHAPTER 20, Malware

https://www.amazon.com/Troubleshooting-Windows-Sysinternals-Tools-2nd/dp/0735684448






Seguimos en el [Día 36](day36.md) 

