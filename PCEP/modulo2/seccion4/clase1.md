# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 4: Variable 
## Clase: Introducción a las variables

### ¿Qué son las Variables?

Hemos estudiado que Python nos permita codificar literales, las cuales contengan valores numéricos y cadenas. Además, se pueden hacer operaciones aritméticas con estos números: sumar, restar, etc. Esto se hará una infinidad de veces en un programa.

Pero, ¿podemos almacenar los resultados de las operaciones, para poder emplearlos en otras operaciones, y así sucesivamente?. ¿Cómo almacenar los resultados intermedios, y después utilizarlos de nuevo para producir nuevos resultados?

Python nos permite guardar los resultados, para ello podemos usar "cajas" (contenedores) especiales para este propósito, estas cajas son llamadas **variables**, el nombre mismo sugiere que el contenido de estos contenedores puede variar en casi cualquier forma.

¿Cuáles son los componentes o elementos de una variable en Python?

* Un nombre.
* Un valor (el contenido del contenedor).

Comencemos con lo relacionado al nombre de la variable:

* Las variables no aparecen en un programa automáticamente. Como desarrollador, tu debes decidir cuantas variables deseas utilizar en tu programa.
* También las debes de nombrar.
* Si se desea nombrar una variable, se deben seguir las siguientes reglas:
    * El nombre de la variable debe de estar compuesto por MAYÚSCULAS, minúsculas, dígitos, y el carácter `_` (guion bajo).
    * El nombre de la variable debe comenzar con una letra.
    * El carácter guion bajo es considerado una letra.
    * Las mayúsculas y minúsculas se tratan de forma distinta (un poco diferente que en el mundo real - Alicia y ALICIA son el mismo nombre, pero en Python son dos nombres de variable distintos, subsecuentemente, son dos variables diferentes).
    * El nombre de las variables no pueden ser igual a alguna de las palabras reservadas de Python (se explicará más de esto pronto).

### Nombres correctos e incorrectos de variables

Nota que la misma restricción aplica a los nombres de funciones.

Python no impone restricciones en la longitud de los nombres de las variables, pero eso no significa que un nombre de variable largo sea mejor que uno corto.

Aquí se muestran algunos nombres de variable que son correctos, pero que no siempre son convenientes:

```
MiVariable, i, t34, Tasa_Cambio, contador, dias_para_navidad, ElNombreEsTanLargoQueSeCometeranErroresConEl, _.
```

Además, Python permite utilizar no solo las letras latinas, sino caracteres específicos de otros idiomas que utilizan otros alfabetos.

Estos nombres de variables también son correctos:

```
Adiós_Señora, sûr_la_mer, Einbahnstraße, переменная.
```

Ahora veamos algunos nombres incorrectos:

`10t` (no comienza con una letra), `Tasa Cambio` (contiene un espacio)

Nota: PEP 8 -- Style Guide for Python Code recomienda la siguiente convención de nomenclatura para variables y funciones en Python:

* Los nombres de las variables deben estar en minúsculas, con palabras separadas por guiones bajos para mejorar la legibilidad (por ejemplo: `var`, `mi_variable`).
* Los nombres de las funciones siguen la misma convención que los nombres de las variables (por ejemplo: `fun`, `mi_función`).
* También es posible usar letras mixtas (por ejemplo: `miVariable`), pero solo en contextos donde ese ya es el estilo predominante, para mantener la compatibilidad retroactiva con la convención adoptada.

### Palabras Clave

Observa las palabras que juegan un papel muy importante en cada programa de Python.

```
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

Son llamadas **palabras clave** o (mejor dicho) **palabras reservadas**. Son reservadas porque no se deben utilizar como nombres: ni para variables, ni para funciones, ni para cualquier otra cosa que se desee crear.

El significado de la palabra reservada está predefinido, y no debe cambiar.

Afortunadamente, debido al hecho de que Python es sensible a mayúsculas y minúsculas, cualquiera de estas palabras se pueden modificar cambiando una o varias letras de mayúsculas a minúsculas o viceversa, creando una nueva palabra, la cual no esta reservada.

Por ejemplo, no se puede nombrar a la variable así:

```
import
```

No se puede tener una variable con ese nombre, esta prohibido, pero se puede hacer lo siguiente:

```
Import
```

