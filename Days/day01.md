
# Amazon S3
#

1.	Como se asignan permisos
2.	Diferencia entre los distintos tipos de storage classes
3.	Que es "Object Storage" y sus casos de uso
4.	Diferencia entre "Object Storage" y "Block Storage"
5.	Se puede usar para dar de alta un sitio web estatico
6.	Como funcionan los triggers y sus casos de uso


#
#




## Funcionamiento


## Amazon Simple Storage Service (Amazon S3) es un servicio de almacenamiento de objetos que ofrece escalabilidad, disponibilidad de datos, seguridad y rendimiento líderes en el sector. 

Clientes de todos los tamaños y sectores pueden almacenar y proteger cualquier cantidad de datos para prácticamente cualquier caso de uso, como los lagos de datos, las aplicaciones nativas en la nube y las aplicaciones móviles. 

Con clases de almacenamiento rentables y características de administración fáciles de utilizar, puede optimizar los costos, organizar los datos y configurar los controles de acceso precisos con objeto de satisfacer requisitos empresariales, organizativos y de conformidad específicos.

![Screenshot_3](https://user-images.githubusercontent.com/105083569/174697721-57995b29-f2b1-483a-a949-7cf41f955471.png)


#
#


## 1.	Como se asignan permisos 
## Gestión de acceso e identidad en Amazon S3

De forma predeterminada, todos los recursos de Amazon S3 (depósitos, objetos y subrecursos relacionados (por ejemplo, lifecycleconfiguración y websiteconfiguración)) son privados. Solo el propietario del recurso, la cuenta de AWS que lo creó, puede acceder al recurso. El propietario del recurso puede otorgar opcionalmente permisos de acceso a otros escribiendo una política de acceso.

Amazon S3 ofrece opciones de políticas de acceso clasificadas ampliamente como políticas basadas en recursos y políticas de usuario. Las políticas de acceso que adjunta a sus recursos (depósitos y objetos) se denominan políticas basadas en recursos . Por ejemplo, las políticas de depósitos y las políticas de puntos de acceso son políticas basadas en recursos. También puede adjuntar políticas de acceso a los usuarios de su cuenta. Estas se denominan políticas de usuario . Puede optar por utilizar políticas basadas en recursos, políticas de usuario o alguna combinación de estas para administrar los permisos de sus recursos de Amazon S3. También puede utilizar listas de control de acceso (ACL) para otorgar permisos básicos de lectura y escritura a otras cuentas de AWS.

De manera predeterminada, cuando otra cuenta de AWS carga un objeto en su depósito de S3, esa cuenta (el escritor del objeto) es propietaria del objeto, tiene acceso a él y puede otorgar acceso a otros usuarios a través de ACL. Puede usar la propiedad de objetos para cambiar este comportamiento predeterminado de modo que las ACL estén deshabilitadas y usted, como propietario del depósito, sea el propietario automático de todos los objetos de su depósito. Como resultado, el control de acceso a sus datos se basa en políticas, como las políticas de IAM, las políticas de depósito de S3, las políticas de punto de enlace de la nube privada virtual (VPC) y las políticas de control de servicios (SCP) de AWS Organizations.

La mayoría de los casos de uso modernos en Amazon S3 ya no requieren el uso de ACL, y le recomendamos que deshabilite las ACL, excepto en circunstancias inusuales en las que necesite controlar el acceso para cada objeto individualmente. Con la propiedad de objetos, puede deshabilitar las ACL y confiar en las políticas para el control de acceso. Cuando deshabilita las ACL, puede mantener fácilmente un depósito con objetos cargados por diferentes cuentas de AWS. Usted, como propietario del depósito, posee todos los objetos del depósito y puede administrar el acceso a ellos mediante políticas. Para obtener más información, consulte Controlar la propiedad de los objetos y deshabilitar las ACL para su depósito .


#
#

## 2. Diferencia entre los distintos tipos de storage classes   
## Clases de almacenamiento de Amazon S3

Amazon S3 ofrece una variedad de clases de almacenamiento entre las cuales puede elegir en función de los requisitos de acceso a los datos, resiliencia y costos de sus cargas de trabajo. Las clases de almacenamiento de S3 se crearon específicamente para brindar el menor costo posible de almacenamiento para los diferentes patrones de acceso. Las clases de almacenamiento de S3 son ideales prácticamente para cualquier caso de uso, incluidos los que cuentan con necesidades de rendimiento demandantes, requisitos de residencia de datos, patrones de acceso desconocidos o cambiantes o almacenamiento de archivos.

Las clases de almacenamiento de S3 incluyen S3 Intelligent-Tiering para el ahorro automático de costos destinado a los datos con patrones de acceso desconocidos o cambiantes; S3 Standard para los datos a los que accede con frecuencia; S3 Standard-Infrequent Access (S3 Standard-IA) y S3 One Zone-Infrequent Access (S3 One Zone-IA) para los datos a los que accede con menor frecuencia; S3 Glacier Instant Retrieval para los datos de archivo que requieren acceso inmediato; S3 Glacier Flexible Retrieval (antes S3 Glacier) para los datos de largo plazo a los que se accede de forma inusual y que no requieren acceso inmediato; y Amazon S3 Glacier Deep Archive (S3 Glacier Deep Archive) para el archivo a largo plazo y la preservación digital con recuperación en horas al costo más bajo de almacenamiento en la nube. Si tiene requisitos de residencia de datos que no puede cumplir en una región de AWS existente, puede utilizar la clase de almacenamiento S3 Outposts para almacenar sus datos de S3 en las instalaciones. Amazon S3 también ofrece capacidades que sirven para administrar sus datos durante todo su ciclo de vida. Una vez configurada una política de ciclo de vida de S3, sus datos se transferirán automáticamente a una clase de almacenamiento distinta sin generar cambios en la aplicación.



## 3. Que es "Object Storage" y sus casos de uso

A medida que los negocios se amplían, usted administra conjuntos de datos en rápido crecimiento pero aislados, provenientes de muchas fuentes y que utiliza un determinado número de aplicaciones y procesos empresariales. En la actualidad, muchas compañías sufren con carteras de almacenamiento fragmentadas que profundizan el nivel de complejidad y demoran el ritmo de innovación de aplicaciones empresariales. El almacenamiento de objetos ayuda a eliminar estos aislamientos mediante el suministro de almacenamiento rentable cuya escala puede ajustarse ampliamente para almacenar cualquier tipo de datos en su formato original. 

Con las soluciones de almacenamiento de objetos de AWS como Amazon Simple Storage Service (Amazon S3) y Amazon Glacier, usted administra el almacenamiento en un único lugar con una interfaz de aplicación fácil de usar. Puede utilizar políticas de uso para optimizar los costos de almacenamiento, alternando entre diferentes clases de almacenamiento automáticamente. AWS facilita el uso de almacenamiento para realizar análisis, obtener información y tomar decisiones con mayor rapidez. 


Con las soluciones de almacenamiento de objetos de AWS como Amazon Simple Storage Service (Amazon S3) y Amazon Glacier, usted administra el almacenamiento en un único lugar con una interfaz de aplicación fácil de usar. Puede utilizar políticas de uso para optimizar los costos de almacenamiento, alternando entre diferentes clases de almacenamiento automáticamente. AWS facilita el uso de almacenamiento para realizar análisis, obtener información y tomar decisiones con mayor rapidez. **


#
#

## Tipos de almacenamiento en la nube


![Screenshot_8](https://user-images.githubusercontent.com/105083569/174700255-db4f1537-533f-48ff-8c0b-94ccc3ec6136.png)


#
#



## 4.Diferencia entre "Object Storage" y "Block Storage"

### ¿Qué es el almacenamiento en bloque?

El almacenamiento en bloque es la forma más antigua y sencilla de almacenamiento de datos. El almacenamiento en bloque almacena datos en fragmentos de tamaño fijo llamados, lo adivinó, "bloques". 

Por sí mismo, un bloque generalmente solo alberga una parte de los datos. 

La aplicación realiza llamadas SCSI para encontrar la dirección correcta de los bloques y luego los organiza para formar el archivo completo.

Debido a que los datos son fragmentarios, la dirección es la única parte de identificación de un bloque; no hay metadatos asociados con los bloques. 

Esta estructura conduce a un rendimiento más rápido cuando la aplicación y el almacenamiento son locales, pero puede generar una mayor latencia cuando están más separados. 

El control granular que ofrece el almacenamiento en bloque lo hace ideal para aplicaciones que requieren alto rendimiento, como aplicaciones transaccionales o de bases de datos.


### Almacenamiento de bloques frente a almacenamiento de objetos

En comparación con el almacenamiento en bloque, el almacenamiento de objetos es mucho más nuevo. Con el almacenamiento de objetos, los datos se empaquetan con etiquetas de metadatos personalizables y un identificador único para formar objetos. 

Los objetos se almacenan en un espacio de direcciones plano y no hay límite para la cantidad de objetos almacenados, lo que facilita mucho el escalado horizontal.

#
#






## 5. Se puede usar para dar de alta un sitio web estatico

Para alojar un sitio web estático en Amazon S3, configure un bucket de Amazon S3 destinado al alojamiento del sitio web y cargue el contenido. Con la consola de administración de AWS, puede configurar el bucket de Amazon S3 como un sitio web estático sin escribir ningún código




## 6.	Como funcionan los triggers y sus casos de uso

La API de desencadenadores describe los tipos de datos y la API relacionados con la creación, actualización o eliminación, y el inicio y la detención de desencadenadores de trabajos en AWS Glue.

## Estructura de TriggerUpdate 
Una estructura usada para proporcionar información que se emplea para actualizar un disparador. Este objeto actualizará la definición del disparador anterior sobrescribiéndola por completo

## Estructura de TriggerUpdate
Una estructura usada para proporcionar información que se emplea para actualizar un disparador. Este objeto actualizará la definición del disparador anterior sobrescribiéndola por completo.








