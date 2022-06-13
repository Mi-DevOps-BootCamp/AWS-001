


# Scripting en BASH
#

## ¿Qué es BASH?


Bash es una herramienta Open Source perteneciente al proyecto GNU, y que fue escrita por Brian Fox. 

Su nombre es el acrónimo de “Bourne-Again Shell”, en referencia a Bourne shell (sh), uno de los primeros intérpretes de comandos de Unix. 

De hecho, Bash hereda muchas propiedades de otras shells como sh, csh o zsh.

Actualmente es la interfaz de línea de comando predeterminada en la mayoría de distribuciones GNU/Linux así como en macOS.

Como ocurre con otras shells de Unix, además de intérprete de comandos, Bash es también un lenguaje de scripting. 

Esto lo hace extremadamente potente para multitud de tareas relacionadas con la administración de sistemas, automatización de tareas.

Para ejecutar múltiples comandos en un solo paso desde el shell, puede escribirlos en una línea y separarlos con punto y coma.
# 
#
## Como empezamos a escribir en BASH

Primero, crea un nuevo archivo usando el comando touch. Al comienzo de cualquier script de Bash, debemos definir qué shell usaremos porque hay muchos shells en Linux, Bash shell es uno de ellos.

La primera línea que escribes al escribir un script bash es el (#!) Seguido del shell que utilizaras.

#! <=== este signo se llama shebang.

![Screenshot_2](https://user-images.githubusercontent.com/96561825/173407011-dc7c4740-0201-4632-8862-b7dad29def3a.png)


Si utilizas el signo de numeral (#) delante de cualquier línea en su script de Bash, esta línea se comentará, lo que significa que no se procesará, pero la línea anterior es un caso especial. 

Esta línea define qué shell utilizaremos, que es el Bash de shell en nuestro caso.

Los comandos de shell se ingresan uno por línea como este:

![Screenshot_3](https://user-images.githubusercontent.com/96561825/173407112-ae8b8e3c-5a15-40df-82f8-0e6f0310ee21.png)

Puedes escribir múltiples comandos en la misma línea, pero debes separarlos con punto y coma, aunque es preferible escribir comandos en líneas separadas, esto hará que sea más fácil de leer luego.

#
#
## Establecer los permisos de scripts 

Después de escribir tu script de Bash, guarda el archivo.

Ahora, configura ese archivo para que sea ejecutable, de lo contrario, mostrará permisos denegados.

![Screenshot_4](https://user-images.githubusercontent.com/96561825/173407239-508d8eb8-f27a-486f-a196-d0de1860451d.png)

Luego intenta ejecutarlo simplemente escribiendo en el shell:

![Screenshot_5](https://user-images.githubusercontent.com/96561825/173407227-f4c846d4-955d-4ebe-ae16-279822707bf8.png)

#
#
## Usando variables

Las variables le permiten almacenar información para usarlas dentro del script.

Puedes definir 2 tipos de variables en tu script de Bash:

● De entorno

● De usuario

#
#
## De entorno

Algunas veces necesitas interactuar con las variables del sistema, puede hacerlo utilizando variables de entorno

![Screenshot_6](https://user-images.githubusercontent.com/96561825/173407352-61c84354-b3a2-447d-8970-26747ab8a347.png)

Observa que ponemos la variable de sistema $ HOME entre comillas dobles, e imprime la variable home correctamente.

#
#
## De usuario


Además, puedes establecer y utilizar variables personalizadas en tu script.

Puedes llamar a las variables de usuario de la misma manera como se muestra a continuación:

![Screenshot_7](https://user-images.githubusercontent.com/96561825/173407419-5b977d58-786e-4d14-b5df-331fe50806f9.png)

#
#

## Sustitución de comando

Puedes extraer información del resultado de un comando utilizando la sustitución de comandos.

Puedes realizar la sustitución de comandos con uno de los siguientes métodos:

● El carácter comilla simple invertida (`).

● El formato $ ().

Asegúrate de que cuando escribes el carácter de comilla invertida, no es la comilla simple.

Debes encerrar el comando con comillas invertidas de la siguiente forma:

![Screenshot_8](https://user-images.githubusercontent.com/96561825/173407545-4b02bba9-fdae-432f-9682-288220f4e849.png)

o a la inversa

![Screenshot_9](https://user-images.githubusercontent.com/96561825/173407534-5d55eaa7-8f8f-4f62-bf79-8a019af72113.png)

Entonces el script podría ser:

![Screenshot_10](https://user-images.githubusercontent.com/96561825/173407626-ff425296-2913-4f04-a12b-5dc96330750c.png)


#
#

## Cálculo Matemático

Puedes realizar cálculos matemáticos básicos utilizando la sintaxis $ ((2 + 2)):


![Screenshot_11](https://user-images.githubusercontent.com/96561825/173407700-4e742a78-561b-45f9-989c-d3ad9b5e9e7f.png)


#
#

## Sentencia If-Then


Tus scripts de Bash necesitarán condicionales. Si el valor es menor que 10, haz esto, sino haz aquello. Puedes imaginar cualquier lógica que quieras.

La estructura más básica de la sentencia if-then es así:

if comand; then

hacer algo

fi

![Screenshot_12](https://user-images.githubusercontent.com/96561825/173407808-1be1698a-f4bd-421c-bb19-1f6644a51b06.png)

![Screenshot_13](https://user-images.githubusercontent.com/96561825/173407816-153d7d70-906c-456a-94ad-206686dd39ec.png)



Dado que el comando whoami devolverá mi usuario, la condición volverá a ser verdadera e imprimirá el mensaje.

#
#
## Sentencia if-then-else


La sentencia if-then-else statement toma la siguiente estructura:

if comand; then
hacer algo
else
hacer otra cosa
fi


Si el comando se ejecuta y retorna cero; lo cual significa éxito, no ejecuta los comandos después de la sentencia else, por otro lado, si la sentencia if retorna un número distinto de cero; lo cual significa que la condición no se cumple, en este caso, el shell ejecuta los comandos después de la sentencia else.

![Screenshot_14](https://user-images.githubusercontent.com/96561825/173407917-4e37a8ec-e9f6-49b4-9ee9-6a8e5e9b73f9.png)

![Screenshot_15](https://user-images.githubusercontent.com/96561825/173407902-18670e17-2e8e-4cc0-a952-e3c7645d22f4.png)


#

#
#
## Comparaciones Numéricas

Puedes realizar una comparación numérica entre dos valores numéricos utilizando
comprobaciones numéricas de comparación como esta:

****number1 -eq number2**** Comprueba si number1 es igual a number2.

****number1 -ge number2**** Comprueba si number1 es más grande o igual number2.

****number1 -gt number2**** Comprueba si number1 es más grande que number2.

****number1 -le number2**** Comprueba si number1 es más pequeño o igual number2.

****number1 -lt number2**** Comprueba si number1 es más pequeño que number2.

****number1 -ne number2**** Comprueba si number1 no es igual a number2.



Ten en cuenta que la sentencia de comparación se encuentra entre corchetes, como se muestra.

![Screenshot_16](https://user-images.githubusercontent.com/96561825/173408000-95538516-3b0e-4bae-9db3-f455e6ac886c.png)


#
#

## Comparaciones de cadenas


Puedes comparar cadenas con una de las siguientes maneras:

****string1 = string2**** Comprueba si string1 es idéntico a string2.

****string1! = string2**** Comprueba si string1 no es idéntico a string2.

****string1 <string2**** Comprueba si string1 es menor que string2.

****string1> string2**** Comprueba si string1 es mayor que string2.

****-n string1**** Comprueba si string1 es más mayor que cero.

****-z string1**** Comprueba si string1 tiene una longitud de cero.




Podemos aplicar la comparación de cadenas en nuestro ejemplo:

![Screenshot_17](https://user-images.githubusercontent.com/96561825/173408093-d3adc6e1-f5c2-4f88-b000-b3fc7eead628.png)

#
#

## Realizamos un ejemplo en BASH


Recordamos que para este ejemplo debemos tener en ejecución alguna de las máquinas virtuales de clase 2.

● Instalamos cowsay sudo apt-get update y sudo apt-get install cowsay

● Vamos a crear una carpeta llamada compras con el comando mkdir (mkdir compras)

● Creamos un file usando el comando sudo nano lista_verduras y lo llenamos con 4 verduras a elección (una por línea)

● Creamos otro file, pero esta vez desde cat>lista_frutas e ingresamos 4 frutas a elección, salimos de cat con CTRL+C

● Mostramos listas cat -n lista_verduras lista_frutas

● Creamos el Script mediante sudo nano lista_compras.sh y lo editamos agregando un pipe para usar cowsay en el resultado

![Screenshot_18](https://user-images.githubusercontent.com/96561825/173408177-a20fc288-ae03-4ddd-823d-e6254d95214d.png)

![Screenshot_20](https://user-images.githubusercontent.com/96561825/173408910-322de263-d742-44b2-b992-cda56de7e44d.png)


● Le damos permisos de ejecución mediante el comando: sudo chmod +x lista_compras.sh

● Ejecutamos el script: ./lista_compras.sh


#
#
#
#
#
Seguimos en el [Día 16](day16.md)

















