
# Amazon Elastic Block Store (EBS)

#

### Cómo funciona

Amazon Elastic Block Store (Amazon EBS) es un servicio de almacenamiento en bloque fácil de usar, escalable y de alto rendimiento diseñado para Amazon Elastic Compute Cloud (Amazon EC2).


![Screenshot_5](https://user-images.githubusercontent.com/105083569/174698642-63999772-64dd-4f8a-9e66-0b277f1043d5.png)


#

![Screenshot_6](https://user-images.githubusercontent.com/105083569/174698675-38bae74d-8163-41de-a4b8-30005c324148.png)



# 1.	Que es "Block Storage" y sus casos de uso


¿Qué es el  Object Storage?
El almacenamiento de objetos (también conocido como almacenamiento basado en objetos Object-based storage) es un término general que se refiere a la forma en que las organizamos y trabajamos con unidades de almacenamiento, mismas que llamamos objetos. Cada objeto contiene tres cosas:
Los datos en sí. Los datos pueden ser cualquier cosa que desee almacenar, desde una foto familiar hasta un manual de 400,000 páginas para ensamblar una aeronave.
Una cantidad expansible de metadatos. Los metadatos están definidos por quien crea el almacenamiento de objetos; contiene información contextual sobre qué datos son, para qué se debe usar, su confidencialidad o cualquier otra cosa que sea relevante para la forma en que se utilizan los datos.
Un identificador global único. El identificador es una dirección dada al objeto para que el objeto se encuentre sobre un sistema distribuido. De esta forma, es posible encontrar los datos sin tener que conocer la ubicación física de los datos (que podrían existir en diferentes partes de un centro de datos o en diferentes partes del mundo)



# 2.	Diferencia entre "Object Storage" y "Block Storage"


![Screenshot_10](https://user-images.githubusercontent.com/105083569/174704738-15ec4ef1-9295-4bc8-a77d-de442359936d.png)

Con el Block Storage (almacenamiento en bloques), los archivos se dividen en bloques de datos de tamaño uniforme, cada uno con su propia dirección pero sin información adicional (metadatos) que proporcione más contexto de lo que es ese bloque de datos. Se puede encontrar almacenamiento en bloque en la mayoría de las cargas de trabajo empresariales. El Block Storage tiene una amplia variedad de usos (como se ve por el aumento en la popularidad de las matrices SAN).

El Object Storage (almacenamiento de objetos), por el contrario, no divide los archivos en bloques de datos sin formato. En cambio, grupos enteros de datos se almacenan en, sí, un objeto que contiene los datos, los metadatos y el identificador único. No hay límite en el tipo o la cantidad de metadatos, lo que hace que el almacenamiento de objetos sea poderoso y personalizable. Los metadatos pueden incluir cualquier cosa, desde la clasificación de seguridad del archivo dentro del objeto hasta la importancia de la aplicación asociada con la información. Cualquiera que haya almacenado una imagen en Facebook o una canción en Spotify ha utilizado el almacenamiento de objetos incluso si no lo sabe. En el centro de datos de la empresa, el almacenamiento de objetos se utiliza para estos mismos tipos de necesidades de almacenamiento, donde los datos deben estar altamente disponibles y ser muy duraderos.

Sin embargo, el almacenamiento de objetos generalmente no le proporciona la capacidad de editar incrementalmente una parte de un archivo (como lo hace el almacenamiento en bloques). Los objetos deben manipularse como una unidad completa, requiriendo que se acceda,actualice y, a continuación, vuelva a escribir el objeto completo en su totalidad. Eso puede tener implicaciones de rendimiento.

Otra diferencia clave es que el sistema operativo puede acceder directamente al almacenamiento de bloques como un volumen de unidad montado, mientras que el almacenamiento de objetos no puede hacerlo sin una degradación significativa del rendimiento. La compensación aquí es que, a diferencia del almacenamiento de objetos, la sobrecarga de administración de almacenamiento de almacenamiento en bloque (como la reasignación de volúmenes) es relativamente inexistente.

## ¿Qué problemas resuelve el almacenamiento de objetos?

El almacenamiento de objetos es ideal para resolver los crecientes problemas de crecimiento de datos. A medida que se generan más y más datos, los sistemas de almacenamiento deben crecer al mismo ritmo. ¿Qué sucede cuando intenta expandir un sistema de almacenamiento basado en bloques más allá de cien terabytes o más allá de varios petabytes? Puede encontrarse con problemas de durabilidad, grandes limitaciones con la infraestructura de almacenamiento que tiene actualmente, o con los gastos generales de administración que pueden llegar al techo.

La solución de problemas de administración de aprovisionamiento presentada por la expansión del almacenamiento en esta escala es donde brilla el almacenamiento de objetos. Los elementos como el contenido web estático, la copia de seguridad de datos y los archivos son casos de uso fantásticos. Las arquitecturas de almacenamiento basadas en objetos se pueden escalar y administrar simplemente agregando nodos adicionales. La organización del espacio de nombre plano de los datos, en combinación con su funcionalidad de metadatos expandibles, facilita esta facilidad de uso.

Otra ventaja de objetar el almacenamiento es su capacidad de respuesta a la necesidad de resiliencia a la vez que mitiga los costos. Los objetos permanecen protegidos almacenando múltiples copias de datos a través de un sistema distribuido; si uno o más nodos fallan, los datos aún pueden estar disponibles, en la mayoría de los casos, sin que la aplicación o el usuario final se vean afectados. (¿Tiempo de inactividad? ¿Qué tiempo de inactividad?) En la mayoría de los casos, se almacenan al menos tres copias de cada archivo. Esto resuelve problemas comunes que incluyen fallas en el disco, rotura de bit, servidor y fallas, y cortes de energía. Este diseño de almacenamiento distribuido para alta disponibilidad permite que se use hardware básico menos costoso porque la protección de datos está integrada en la arquitectura del objeto.


#
#
# 4.	Como crear un volumen

Puede crear un volumen de Amazon EBS y, a continuación, adjuntarlo a cualquier instancia de EC2 en la misma zona de disponibilidad. Si crea un volumen de EBS cifrado, solo puede adjuntarlo a los tipos de instancia admitidos. Para obtener más información, consulte Tipos de instancias admitidos.

Si va a crear un volumen para un escenario de almacenamiento de alto rendimiento, debe asegurarse de utilizar un volumen de SSD de IOPS provisionadas (io1 o io2) y adjuntarlo a una instancia que disponga de ancho de banda suficiente para admitir la aplicación, como, por ejemplo, una instancia optimizada para EBS. El mismo consejo es aplicable a los volúmenes de HDD con rendimiento optimizado (st1) y de HDD en frío (sc1). Para obtener más información, consulte Instancias optimizadas para Amazon EBS.

Los volúmenes de EBS nuevos disponen de su máximo rendimiento en cuanto están disponibles y no es necesario inicializarlos (proceso que antes se denominaba precalentamiento). No obstante, debe inicializar los bloques de almacenamiento en los volúmenes creados a partir de instantáneas (extraídas de Amazon S3 y grabadas en el volumen) para poder obtener acceso al bloque. Esta acción preliminar lleva tiempo y puede provocar un aumento considerable de la latencia de una operación de E/S la primera vez que se obtiene acceso a cada bloque. El rendimiento del volumen se alcanza después de descargar todos los bloques y de escribirlos en el volumen. Para la mayoría de las aplicaciones, la amortización de este costo a lo largo de la vida útil del volumen es aceptable. Para evitar este impacto inicial en el rendimiento en un entorno de producción, puede forzar la inicialización inmediata de todo el volumen o habilitar la restauración rápida de instantáneas. Para obtener más información, consulte Inicializar de volúmenes de Amazon EBS.


#
#
#5.	Como sacar snapshots

Instantáneas de Amazon EBS

Puede hacer una copia de seguridad de los datos contenidos en los volúmenes de Amazon EBS en Amazon S3 tomando instantáneas de un momento dado. Las instantáneas son copias de seguridad incrementales, lo que significa que solo se guardan los bloques que han cambiado en el dispositivo después de la instantánea más reciente. Esto disminuye el tiempo necesario para crearlo y ahorra costos de almacenamiento, ya que no se duplican los datos. Cada instantánea contiene toda la información necesaria para restaurar los datos (del momento en que se tomó) en un volumen de EBS nuevo.

Cuando se crea un volumen de EBS basado en una instantánea, el nuevo volumen comienza como una réplica exacta del volumen original utilizado para crear la instantánea. El volumen replicado carga los datos en segundo plano para que pueda comenzar a utilizarlo inmediatamente. Si tiene acceso a datos que aún no se han cargado, el volumen descarga inmediatamente los datos solicitados de Amazon S3 y después continúa cargando el resto de los datos del volumen en segundo plano. Para obtener más información, consulte Crear instantáneas de Amazon EBS.

Cuando se elimina una instantánea, solo se borran los datos que son únicos de dicha instantánea. Para obtener más información, consulte Eliminar una instantánea de Amazon EBS.


#
#

# 6.	Clases de almacenamiento

Tipos de volúmenes de Amazon EBS

Amazon EBS proporciona los siguientes tipos de volúmenes, que difieren en cuanto a rendimiento y precio, para que pueda adaptar el rendimiento y el costo del almacenamiento a las necesidades de las aplicaciones. Los tipos de volumen se dividen en estas categorías:

Unidades de estado sólido (SSD): están optimizadas para cargas de trabajo de transacciones que implican operaciones de lectura/escritura frecuentes de pequeño tamaño de E/S, en las que el atributo de rendimiento dominante es IOPS

Unidades de disco duro (HDD): están optimizadas para grandes cargas de trabajo de streaming, en las que el atributo de rendimiento dominante es el rendimiento.

Generación anterior: unidades de disco duro que se pueden utilizar para cargas de trabajo con conjuntos de datos pequeños en los que se accede a la información con poca frecuencia y el rendimiento no tiene una importancia primordial. Le recomendamos que considere la posibilidad de utilizar un tipo de volumen de generación actual en su lugar.

Existen varios factores que pueden afectar al rendimiento de los volúmenes de EBS, como la configuración de la instancia, las características de E/S o la demanda de la carga de trabajo. Para utilizar completamente las IOPS aprovisionadas en un volumen de EBS, utilice instancias optimizadas para EBS. Para obtener más información sobre cómo obtener el máximo rendimiento de los volúmenes de EBS, consulte Rendimiento de los volúmenes de Amazon EBS en las instancias de Linux.


#
#
#
#
#


Te veo en el [Dia 4](day04.md).  
