# Malware Hunting con AutoRuns

# Cómo utilizar Autoruns para Detectar Malware



En este desafio continuamos la tecnica de Malware Hunting sobre el Malware JigSaw de nuestra FASE I 

En este desafio, el cual una vez finalizado debemos cargarlo en el drive consignado por el tutor, junto con las capturas de pantalla y la explicacion, seguiremos analizando nuestra VM en busqueda de rastros y muestras de la ejecucion de JIGSAW, nuestra muestra de Malware elegida para esta ocasion.

Comenzemos!

Vamos a comenzar con las nociones básicas para aprender a utilizar Autoruns:

Al entrar en Autoruns, aparecerán todos los procesos que se ejecutan automáticamente en el arranque del ordenador. No obstante, es importante recordar que no mostrará los programas y procesos que Microsoft ha integrado para que se ejecuten en el arranque del PC.
Interfaz

zzzzzzzzzzzz

Ante todo, debemos admitir que Autoruns no tiene una interfaz intuitiva ni agradable a la vista. 

### Es una ventana repleta de pestañas y botones que generan confusión al usuario. Visualmente, parece un programa creado para programadores.

Sin embargo, no es difícil de utilizar después de conocerlo. Solo debes tomarte un tiempo para navegar en el software y conocer sus diferentes funciones


#

## Deshabilitar procesos

zzzzzzzzz

Para desactivar cualquier proceso, solo deberás marcar en la casilla junto al elemento y listo. Repite el procedimiento con todos los elementos de la lista que no necesites para el inicio del ordenador. Reinicia el equipo para que los cambios surtan efecto.

Validación de firmas de código
zzzzzzzzzzzz


Cuando navegues en el menú de opciones encontrarás una función de gran utilidad: ***Verify Code Signatures (Verificación de firmas de código).***

Así sabrás si una firma digital está analizada o verificada. Generalmente, los elementos marcados en rosa no están verificados.


#
# Logon


zzzzzzzzzzzzzzz


Muestra los procesos que se ejecutan automáticamente al arrancar el ordenador. Aquí puedes elegir algunos elementos para que se ejecuten desde el inicio y bloquear los procesos inservibles.

Muestra los componentes complementarios que se pueden cargar de forma automática en el Explorador de Windows.

#
# Internet Explorer


### Es una herramienta que refuerza la seguridad del PC.

Muestra las barras de herramientas, las extensiones y los objetos auxiliares del navegador que suelen utilizar los piratas informáticos para espiar a sus víctimas.


#
# Servicios

zzzzzzzzzzzzzzz

Aquí están los servicios que suelen utilizar los malwares para disfrazar su identidad. Debes tener cuidado de no desactivar elementos importantes para el funcionamiento de Windows.


#
# Drivers

zzzzzzzzzzzzzz

Aparecerán los controladores que puedan estar infectados por un malware u otra amenaza informática.



#
#
# Cómo limpiar manualmente un PC infectado


Con Autoruns puedes eliminar potenciales amenazas del ordenador. 

***Debes desmarcar la casilla junto al proceso que quieres inhabilitar temporalmente. Si quieres desbloquear de forma permanente un programa, puedes hacer clic derecho sobre el elemento y eliminarlo.***

***Nota:*** de esa manera el software solo quedará inactivo, más no desinstalado del PC. Para borrar un programa del ordenador deberás desinstalarlo en el Panel de Control.

#
# Cómo detectar softwares sospechosos

zzzzzzzzz


En ocasiones, hace falta un poco de experiencia para saber qué software representa un peligro y cual no. 

***La mayoría de los elementos que muestra Autoruns son programas legítimos***, aunque sean desconocidos para ti. 

Veamos algunos tips que te ayudarán a diferenciar los softwares legítimos, de aquellos que no lo son.

> Si un elemento está firmado digitalmente por una compañía o tiene una descripción, lo más probable es que sea legítimo

> Si el nombre del software te suena familiar, generalmente no hay ningún problema
> 
Los programas maliciosos **se suelen “disfrazar” con nombres similares a los softwares legítimos**, como “WhatsAppLaucher” o “PhotoshopJump”. Si encuentras elementos de ese tipo, es probable que el ordenador haya sido atacado por un virus

> Generalmente, los malwares aparecen en la pestaña “Logon”, aunque no siempre ocurre así

> Los virus y malwares se suelen esconder en esta carpeta: C:\Windows\System32. Revísala frecuentemente

> Los archivos riesgosos tienden a estar acompañados de un icono genérico









































See you on [Day 32](day32.md) 

