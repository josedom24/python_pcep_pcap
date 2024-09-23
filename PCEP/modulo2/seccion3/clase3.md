# Prioridad de operadores

## Operadores y sus prioridades

Hasta ahora, se ha tratado cada operador como si no tuviera relación con los otros. Obviamente, dicha situación tan simple e ideal es muy rara en la programación real. Lo normal es encontrar en una expresión varios operadores, por ejemplo:

```
2 + 3 * 5
```

Probablemente recordarás de la escuela que las multiplicaciones preceden a las sumas, por lo tanto,  primero se debe multiplicar 3 por 5, mantener el 15 en tu memoria y después sumar el 2, dando como resultado el 17.

El fenómeno que causa que algunos operadores actúen antes que otros es conocido como la **jerarquía de operadores o orden de prioridad de operadores**.

Python define la jerarquía de todos los operadores, y asume que los operadores de mayor jerarquía deben realizar sus operaciones antes que los de menor jerarquía.

Entonces, si se sabe que la `*` tiene una mayor prioridad que la `+`, el resultado final debe de ser obvio.

## Asociatividad de operadores

Nota: En el curso oficial traducido al Español se ha traducido la palabra inglesa *binding* como *enlace*. La traducción más correcta sería *asociatividad*.

La **asociatividad** de un operador determina el orden en que se realizan las operaciones de los operadores con la misma prioridad, los cuales se encuentran dentro de una misma expresión.

La mayoría de los operadores de Python tienen una **asociatividad hacia la izquierda**, lo que significa que el cálculo de la expresión **es realizado de izquierda a derecha**. Por ejemplo:

```
print(9 % 6 % 2)
```

Existen dos posibles maneras de evaluar la expresión:

* De **izquierda a derecha**: primero `9 % 6` da como resultado 3, y entonces `3 % 2` da como resultado 1.
* De **derecha a izquierda**: primero `6 % 2` da como resultado 0, y entonces `9 % 0` causa un **error fatal**.

Ejecuta el ejemplo y observa lo que se obtiene. El resultado debe ser 1. El operador tiene una asociatividad a la izquierda. Pero hay una excepción interesante.

## La asociatividad de la potencia

Repite el experimento, pero ahora con potencias. Por ejemplo:

```
print(2 ** 2 ** 3)
```

Los dos posibles resultados son:

* `2 ** 2` → `4`; `4 ** 3` → `64`
* `2 ** 3` → `8`; `2 ** 8` → `256`


Ejecuta el código, ¿Qué es lo que observas? El resultado muestra claramente que el operador de exponenciación utiliza **asociatividad a la derecha**.

## Lista de prioridades

Como eres nuevo a los operadores de Python, no se presenta por ahora una lista completa de las prioridades de los operadores. En lugar de ello, se mostrarán solo algunos, y se irán expandiendo conforme se vayan introduciendo operadores nuevos. Tabla de prioridades:

1. `+`,`-` (unarios)
2. `**`
3. `*`,`/`,`//`,`%`
4. `+`,`-` (binarios)

Nota: se han enumerado los operadores en orden **de la más alta (1) a la más baja (4) prioridad**.

Intenta solucionar la siguiente expresión:

```
print(2 * 3 % 5)
```

Ambos operadores (`*` y `%`) tienen la misma prioridad, el resultado solo se puede obtener conociendo el sentido del asociatividad. ¿Cuál será el resultado?: **1**.

## Operadores y paréntesis

Por supuesto, se permite hacer uso de paréntesis, lo cual cambiará el orden natural del cálculo de la operación.

De acuerdo con las reglas aritméticas, las sub-expresiones dentro de los paréntesis siempre se calculan primero.

Se pueden emplear tantos paréntesis como se necesiten, y seguidos son utilizados para mejorar la legibilidad de una expresión, aun si no cambian el orden de las operaciones.

Un ejemplo de una expresión con múltiples paréntesis es la siguiente:

```
print((5 * ((25 % 13) + 100) / (2 * 13)) // 2)
```

Intenta calcular el valor que se calculará en la consola. ¿Cuál es el resultado de la función `print()`?: **10**.

