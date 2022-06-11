
# Analisis de Procesos en Memoria Virtual con VMMAP  

#
#



En este desafío continuamos la técnica de Malware Hunting sobre el Malware JigSaw de nuestra FASE 1

![Screenshot_12](https://user-images.githubusercontent.com/96561825/173207124-abfd540c-2a48-447b-be21-f07a3c5e08be.png)


En este desafío, el cual una vez finalizado debemos cargarlo en el drive consignado por el tutor, junto con las capturas de pantalla y la explicación, seguiremos analizando nuestra VM en búsqueda de rastros y muestras de la ejecución de JIGSAW, nuestra muestra de Malware elegida para esta ocasión.

![Screenshot_13](https://user-images.githubusercontent.com/96561825/173207127-b1beea54-a58d-4a13-b830-9bd8fa91cb42.png)




¿Cuáles son los requisitos de la entrega? :

Aquí deberemos entregar las capturas de los procesos infectados y sus sectores de memoria virtual, VM infectada con Jigsaw.
Valoraremos también las capturas del proceso infectado dentro de VMMAP.

¡Comencemos!

#
#
# BREVE  EXPLICACIÓN DE CADA HERRAMIENTA
#
#
# RAMMAP

![Screenshot_14](https://user-images.githubusercontent.com/96561825/173207132-2282fd67-55f8-473c-8d18-615fb32dabdb.png)



La gestión de memoria RAM en Windows deja mucho que desear. Esto no es algo nuevo, sino que se extiende a tiempos muy remotos.

A medida que la cantidad de RAM disponible en los sistemas aumenta, sus deficiencias de administración se sienten menos, pero si debes trabajar con ordenadores limitados en memoria o con aplicaciones que viven de fuga en fuga, tal vez quieras descargar una copia de RAMMap, herramienta del inagotable Mark Russinovich, bajo la división Sysinternals de Microsoft.


![Screenshot_15](https://user-images.githubusercontent.com/96561825/173207134-3a06a388-4787-43ee-bb0e-80c260513bc5.png)




#
# VMMAP

![Screenshot_16](https://user-images.githubusercontent.com/96561825/173207136-f21d9835-edf4-460c-a1e3-b0a66d52f9ad.png)

Podemos descargar la herramienta desde este link.https://docs.microsoft.com/en-us/sysinternals/downloads/vmmap

![Screenshot_17](https://user-images.githubusercontent.com/96561825/173207139-3b8195fe-ab08-4899-9488-b162194b658f.png)


VMMap es una utilidad de análisis de memoria física y virtual de proceso. 

Muestra un desglose de los tipos de memoria virtual confirmados de un proceso, así como la cantidad de memoria física (espacio de trabajo) asignada por el sistema operativo a esos tipos. 

Además de las representaciones gráficas del uso de memoria, VMMap también muestra información de resumen y un mapa de memoria de proceso detallado. Las eficaces funcionalidades de filtrado y actualización permiten identificar los orígenes de uso de memoria de proceso y el costo de memoria de las características de la aplicación.

Además de las vistas flexibles para analizar procesos activos, VMMap admite la exportación de datos en varios formatos, incluido un formato nativo que conserva toda la información para que pueda volver a cargarlos. También incluye opciones de línea de comandos que permiten escenarios de scripting.

VMMap es la herramienta ideal para desarrolladores que desean comprender y optimizar el uso de recursos de memoria de la aplicación.















#
#
#
#
#

Nos vemos el [Dia 28](day28.md)  
