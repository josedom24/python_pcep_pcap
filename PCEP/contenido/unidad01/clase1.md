# Introducción a la programación y a los lenguajes de programación

## Programas de ordenador

* Un **programa** hace que podamos usar un ordenador. Un ordenador, sin **programa** no puede realizar ninguna operación, no sirve para nada.
* Para que un ordenador realice un proceso, se le debe suministrar en primer lugar un **algoritmo** adecuado, que llamamos programa.
* En realidad, un ordenador sólo puede realizar operaciones básicas con números (sumas, restas,...). Estas operaciones la realiza de manera muy rápida y con la posibilidad de repetirlas tanta veces como haga falta.

* Por ejemplo, si queremos calcular la velocidad media que has alcanzado durante un viaje largo. Conoces la distancia, conoces el tiempo, necesitas la velocidad.
    * El ordenador, podrá calcularlo, pero no entiende conceptos como distancia, velocidad o el tiempo. Por lo tanto, necesitamos indicarle al ordenador los siguientes pasos:
        * Que lea un número que represente la distancia;
        * Que lea un número que represente el tiempo de viaje;
        * Qué divide el valor anterior por el segundo y almacenar el resultado en la memoria;
        * Que muestre el resultado (que representa la velocidad promedio) en un formato legible.

* Estos pasos forman el **algoritmo** para resolver el **problema**, el **algoritmo** lo tendremos que traducir a un lenguaje que entienda el ordenador y crear un **programa**, para ello utilizamos distintos lenguajes a los que llamamos **lenguajes de programación**.

## Lenguajes naturales y lenguajes de programación

### Lenguaje natural

* Un lenguaje es un medio (y una herramienta) para expresar y registrar pensamientos.
* Ejemplos: lenguaje corporal (no utiliza palabras), nuestra lengua materna,...
* El **lenguaje natural**, que es el que las personas utilizamos para comunicarnos, el número de palabras y combinaciones que podemos realizar es muy grande y complejo.
* El ordenador no entiende el lenguaje natural.

### Lenguaje máquina

* El **lenguaje máquina** es un lenguaje de programación que directamente entiende el ordenador, ya que sus instrucciones son cadenas binarias (secuencias de ceros y unos) que especifican una operación y las posiciones (dirección) de memoria implicadas en la operación.
* Este lenguaje es muy rudimentario y solemos llamarlo **código máquina**.
* Cada tipo de procesador (arquitectura) tiene un conjunto de instrucciones muy básicas que sabe ejecutar. A este conjunto completo de comandos conocidos se llama **lista de instrucciones**.

## ¿Qué compone a un lenguaje?

Podemos decir que cada lenguaje (máquina o natural, no importa) consta de los siguientes elementos:

* Un **alfabeto**: conjunto de símbolos utilizados para formar palabras de un determinado lenguaje. (Alfabeto latino, cirílico, kanji,...)
* Un **léxico**: (también conocido como diccionario) un conjunto de palabras que el lenguaje ofrece a sus usuarios. Por ejemplo, la palabra "ordenador" en español, y en inglés se usa "computer".
* Una **sintaxis**: conjunto de reglas (formales o informales, escritas o interpretadas intuitivamente) utilizadas para precisar si una determinada cadena de palabras forma una oración válida.
* Una **semántica**: Conjunto de reglas que determinan si una frase tiene sentido.

## Lenguaje máquina y lenguaje de alto nivel

* Podemos usar el **lenguaje máquina** para comunicarnos directamente con el ordenador.
* Pero, el **lenguaje máquina** está muy lejos del **lenguaje natural**, y tanto su léxico, como su sintaxis y semántica es complicada para el ser humano.
* Es por lo que necesitamos, un lenguaje común para ordenadores y humanos, o un puente entre los dos mundos diferentes. 
* Necesitamos un lenguaje en el que los humanos puedan escribir sus programas y que los ordenadores puedan usar para ejecutar los programas. Este lenguaje será mucho más complejo que el lenguaje de máquina y, sin embargo, mucho más simple que el lenguaje natural.
* A este tipo de lenguaje se le llama **lenguaje de programación de alto nivel**.
    * Los lenguajes de alto nivel son los mas utilizados por los programadores. 
    * Están diseñados para que las personas escriban y entiendan los programas de un modo mucho más fácil que los lenguajes máquina. 
    * Un programa escrito en un lenguaje de alto nivel es independiente del tipo de ordenador (no depende del tipo de hardware).
    * Los programas escritos en lenguajes de alto nivel son portables o transportables, lo que significa la posibilidad de poder ser ejecutados con poca o ninguna modificación en diferentes tipos de ordenadores.
    * Un programa escrito en un lenguaje de programación de alto nivel se denomina **código fuente** (en contraste con el código máquina ejecutado por los ordenadores). Del mismo modo, el archivo que contiene el código fuente se denomina **archivo fuente**.
    * Python es un lenguaje de programación de alto nivel.

