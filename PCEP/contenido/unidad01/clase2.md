# Compilación e interpretación

## Escribir un programa

* Cuando queremos que un ordenador realice un proceso complejo, escribiremos un programa en un lenguaje de programación de alto nivel.
* El programa debe ser correcto en diferentes niveles:
  * **Alfabéticamente**: un programa debe estar escrito en un alfabeto reconocible, por ejemplo, Python se escribe en alfabeto latino.
  * **Léxicamente**: cada lenguaje de programación tiene su diccionario. Afortunadamente es mucho más simple y pequeño que el diccionario de cualquier idioma natural.
  * **Sintácticamente**: cada lenguaje tiene sus reglas y hay que obedecerlas.
  * **Semánticamente**:  el programa tiene que tener sentido.
* Al escribir el programa se pueden producir **errores** en cada uno de estos cuatro aspectos.
* Una vez escrito el programa sin errores, necesitamos **traducir** nuestro programa a código máquina. Afortunadamente, la traducción la puede hacer un programa de ordenador (**traductor**), lo que hace que todo el proceso sea rápido y eficiente. 

## Tipos de traductores

* Hay dos formas diferentes de transformar un programa de un lenguaje de programación de alto nivel a un lenguaje de máquina (dos tipos de traductores):
    * **Compilación**: 
        * El programa fuente se traduce una vez (si se modifica hay que volver a traducirlo). 
        * Sii se encuentran errores se informarán de los mismos y no se genera fichero ejecutable.
        * Se genera un fichero ejecutable con el código máquina que podemos ejecutar en distintos ordenadores del mismo tipo. 
        * El fichero generado depende del tipo de ordenador y sistema operativo (si compilamos para Windows sólo funciona en este sistema operativo).
        * El programa que realiza la compilación se denomina **compilador**.
    * **Interpretación**: 
        * Lee el programa (código fuente) de una archivo de **texto plano**.
        * Se traduce el programa línea por línea.
        * Se debe traducir el código fuente cada vez que vamos a ejecutar el programa.
        * Por lo tanto, es necesario tener el archivo fuente.
        * El programa que realiza la interpretación se denomina **interprete**.
        * En el ordenador donde se ejecute el programa necesitamos tener un interprete.
        * Si el traductor encuentra algún error, dependiendo del tipo, puede abortar la ejecución desde el principio, o informar del error cuando llega a la línea donde se ha producido.
        * El interprete informará de donde ha encontrado el error. En ocasiones el lugar y la causa del error no se indican de forma correcta, ya que el error se ha causado en instrucciones anteriores.

## Ventajas y Desventajas

**Compilación**:

* Ventajas:
    * La ejecución del código traducido suele ser más rápida.
    * Solo el programador debe tener el compilador; el usuario final puede usar el programa sin él.
    * El código traducido se almacena en lenguaje máquina y se ejecuta directamente en el ordenador.
    * No es necesario tener el código fuente para utilizar el programa.
* Desventajas:
    * La compilación en sí misma puede llevar mucho tiempo; es posible que no puedas ejecutar tu código inmediatamente después de cualquier modificación.
    * Tienes que tener tantos compiladores como plataformas de hardware en las que deseas que se ejecute tu código.

**Interpretación**
* Ventajas:
    * Puedes ejecutar el código en cuanto lo completes; no hay fases adicionales de traducción.
    * El código se almacena utilizando el lenguaje de programación, no el de la máquina; esto significa que puede ejecutarse en ordenadores que utilizan diferentes lenguajes máquina; no se compila el código por separado para cada arquitectura diferente.
* Desventajas:
    * Normalmente la ejecución de un programa interpretado es más lenta.
    * Tanto tú como el usuario final deben tener el intérprete y el código para ejecutar el programa.

## Conclusiones

* **Python es un lenguaje interpretado**. Esto significa que hereda todas las ventajas y desventajas descritas. 
* Si deseas programar en Python, necesitarás el **intérprete de Python**. No podrás ejecutar tu código sin él. Afortunadamente, Python es gratis. Esta es una de sus ventajas más importantes.
* Debido a razones históricas, los lenguajes diseñados para ser utilizados en la manera de interpretación a menudo se llaman **lenguajes de scripting**, mientras que los programas fuente codificados que los usan se llaman **scripts**.