# Introduccion a Desafios de Fase I del BootCamp DevOps Enginner.
##


![Screenshot_43](https://user-images.githubusercontent.com/96561825/173430665-82d3ce92-e18e-4239-a26e-8ee4c1c3437d.png)

#
#

Teniendo en cuenta el avance y la completitud de los ejercicios y actividades de los cursos activados en la plataforma de Alumni

- Administracion de Windows Server
- Seguridad en Windows.


Los desafios que trabajaremos a lo largo de la Fase I del BootCamp, en la etapa Windows,e staran centrados en analizar de manera dinamica y estatica malware activo y real en un entorno seguro en Windows, tanto en la nube como en una maquina virtual con VirtualBox.

Para ello, necesitaremos lo siguiente:

- Desplegar una Maquina Virtual con Windows 7 en Virtualbox, para eso utilizaremos las guias
- Instalar VirtualBox : https://drive.google.com/file/d/1DBFGp2OIFE0EzL5shf-_fA0at0hXp6kL/view?usp=sharing 
- Pedir link de Iso de Windows 7 para virtual box al tutor.
- Crear una VM con Windows con VirtualBox con Windows 7  : Desafio Inicial  - Instalar Windows en VirtualBox
- Descargar un repositorio de malware para estudio desde : https://github.com/ytisf/theZoo/archive/refs/heads/master.zip

( Sitio oficial : https://thezoo.morirt.com/ )  

![Screenshot_44](https://user-images.githubusercontent.com/96561825/173431170-3fc71560-4d03-48ca-bd41-1e6148aaeb88.png)


Una vez descargado este repositorio, veremos todas las muestras de malware que recopila.


Estas se encuentran dentro de la carpeta “Malware”

![Screenshot_45](https://user-images.githubusercontent.com/96561825/173431367-ab16f703-ee86-4ab5-b8d4-b3d3846bd83c.png)



Y dentro de la carpeta “Binaries”

y seleccionaremos JigSaw

![Screenshot_46](https://user-images.githubusercontent.com/96561825/173431398-2fd5daaf-ea80-435c-a362-213a042b5dc0.png)

![Screenshot_47](https://user-images.githubusercontent.com/96561825/173431406-4edf6e2f-9141-4868-ba6a-5995bafa35ef.png)


descargaremos este malware en NUESTRA MAQUINA VIRTUAL, esto quiere decir que este enlace y la descarga del mismo debe darse dentro de la VM con Windows
#
## PRESTAR ATENCION A LO ENSEÑADO EN CLASE - 

Las muestras de malware deben ser manipuladas de acuerdo a lo enseñado en clase y EducacionIT se desliga totalmente de cualquier responsabilidad, en el caso de una manipulacion irresponsable del mismo.

Deberemos descomprimir Jigsaw en nuestra VM, en el escritorio.

![Screenshot_48](https://user-images.githubusercontent.com/96561825/173431514-c8dbad4e-cd45-4048-9c2c-d3e5d90570ce.png)

Podes encontrar el ransomware aquí , pero le sugiero que use una VM antes de ejecutar el ejecutable. 

Bien, una vez que haya descargado y extraído el archivo exec, ejecútelo en su máquina virtual. 

Prefiero usar Windows 7/8 porque las versiones más nuevas de Windows se actualizan con frecuencia con parches de seguridad y vienen habilitados con defensores que pueden bloquear algunos de los procesos incluso después de deshabilitar el defensor.

Usaré Windows 7. 

Así que una vez que ejecutes el archivo jigsaw.exe, espera unos segundos y luego verás algo como esto en tu pantalla (de la VM)

Este es el link 

https://github.com/ytisf/theZoo/blob/master/malware/Binaries/Ransomware.Jigsaw/Ransomware.Jigsaw.zip


![Screenshot_49](https://user-images.githubusercontent.com/96561825/173431656-ce729f10-7246-4e67-88ac-3735727a89c0.png)

Haga clic en Aceptar y espere un poco más de tiempo y luego verá algo como esto.


Nuestro desafio principal a lo largo de la FASE I del BootCamp sera darle caza a este Malware, mediante la Suite Systernals ( https://docs.microsoft.com/en-us/sysinternals/downloads/) en sistemas Windows.


Para finalizar, descargaremos la suite Systernals desde


https://docs.microsoft.com/en-us/sysinternals/downloads/



![Screenshot_50](https://user-images.githubusercontent.com/96561825/173431762-23986fea-fba3-460c-99e4-5ada21c7b626.png)

Así que ahora sabemos que el archivo jigsaw.exe se ejecutó con éxito y debe haber inyectado algún proceso malicioso. 


#
#
#
#
#

Seguimos en el [Día 32](day32.md) 

