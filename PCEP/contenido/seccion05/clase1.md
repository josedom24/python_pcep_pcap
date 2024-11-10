# Introducción a las variables

## ¿Qué son las variables?

Hemos estudiado que Python nos permita codificar literales, las cuales contengan valores numéricos y cadenas. Además, se pueden hacer operaciones aritméticas con estos números: sumar, restar, etc. 

Pero, ¿podemos almacenar los datos y los resultados de las operaciones, para poder emplearlos en otras operaciones, y así sucesivamente?. ¿Cómo almacenar los resultados intermedios, y después utilizarlos de nuevo para producir nuevos resultados?

Python nos permite guardar los resultados, para ello podemos usar "cajas" (contenedores) especiales para este propósito, estas cajas son llamadas **variables**, el nombre mismo sugiere que el contenido de estos contenedores puede variar en casi cualquier forma.

¿Cuáles son los componentes o elementos de una variable en Python?

* Un nombre.
* Un valor (el contenido del contenedor).

## Nombres correctos e incorrectos de variables

Comencemos con lo relacionado al nombre de la variable:

* El programa define las variables que necesita y su nombre.
* Si se desea nombrar una variable, se deben seguir las siguientes reglas:
    * El nombre de la variable debe de estar compuesto por MAYÚSCULAS, minúsculas, dígitos, y el carácter `_` (guión bajo).
    * Python permite utilizar no solo las letras latinas, sino caracteres específicos de otros idiomas que utilizan otros alfabetos.
    * El nombre de la variable debe comenzar con una letra.
    * El carácter guión bajo es considerado una letra.
    * Las mayúsculas y minúsculas se tratan de forma distinta `Alicia` y `ALICIA` son dos variables distintas.
    * El nombre de las variables no pueden ser igual a alguna de las palabras reservadas de Python. 
        * Las **palabras clave** o  **palabras reservadas** corresponde a las distintas instrucciones que podemos usar en Python. Algunas de ellas son:
             ```
            ['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise',                   'return', 'try', 'while', 'with', 'yield']
             ```
* Los nombres de las variables deben mejorar la claridad del código indicando que dato se guarda en dicha variable.

La guía de estilo para código python (**PEP 8, Style Guide for Python Code**) recomienda la siguiente convención de nomenclatura para variables y funciones en Python:
 
* Los nombres de las variables deben estar en minúsculas, con palabras separadas por guiones bajos para mejorar la legibilidad (por ejemplo: `var`, `mi_variable`).
* Los nombres de las funciones siguen la misma convención que los nombres de las variables (por ejemplo: `fun`, `mi_función`).
* También es posible usar letras mixtas (por ejemplo: `miVariable`), pero solo en contextos donde ese ya es el estilo predominante, para mantener la compatibilidad retroactiva con la convención adoptada.

## Tipo de datos de una variable

Una variables es un identificador que referencia a un valor. No hay que declarar la variable antes de usarla, el tipo de la variable será el mismo que el del valor al que hace referencia. Por lo tanto su tipo puede cambiar en cualquier momento:

```bash
var = 5
type(var)
<class 'int'>
var = "hola"
type(var)
<class 'str'>
```
