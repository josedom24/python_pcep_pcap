# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 3: Operadores, herramientas de manipulación de datos 
## Clase: Resumen y cuestionario de la sección

## Resumen de sección

1. Una **expresión** es una combinación de valores (o variables, operadores, llamadas a funciones, aprenderás de ello pronto) las cuales son evaluadas y dan como resultado un valor, por ejemplo, `1 + 2`.

2. Los **operadores** son símbolos especiales o palabras clave que son capaces de operar en los valores y realizar operaciones matemáticas, por ejemplo, el `*` multiplica dos valores: `x * y`.

3. Los operadores aritméticos en Python: `+` (suma), `-` (resta), `*` (multiplicación), `/` (división clásica: regresa un flotante siempre), `%` (módulo: divide el operando izquierdo entre el operando derecho y regresa el residuo de la operación, por ejemplo, `5 % 2 = 1`), `**` (exponenciación: el operando izquierdo se eleva a la potencia del operando derecho, por ejemplo, `2 ** 3 = 2 * 2 * 2 = 8`), `//` (división entera: retorna el número resultado de la división, pero redondeado al número entero inferior más cercano, por ejemplo, `3 // 2.0 = 1.0`).

4. Un **operador unario** es un operador con solo un operando, por ejemplo, `-1`, o `+3`.

5. Un **operador binario** es un operador con dos operados, por ejemplo, `4 + 5`, o `12 % 5`.

6. Algunos operadores actúan antes que otros, a esto se le llama **jerarquía de operadores**:

    * Unario `+` y `-` tienen la prioridad más alta.
    * Después: `**`, después: `*`, `/`, `//` y `%`, y después la prioridad más baja: binaria `+` y `-`.

7. Las sub-expresiones **dentro de paréntesis siempre se calculan primero**, por ejemplo, `15 - 1 * ( 5 *( 1 + 2 ) ) = 0`.

8. Los operadores de exponenciación utilizan asociatividad a la derecha, por ejemplo, `2 ** 2 ** 3 = 256`. Los demás suelen usar asociatividad a la izquierda.

## Cuestionario de sección

1. ¿Cuál es la salida del siguiente fragmento de código? 

    ```
    print((2 ** 4), (2 * 4.), (2 * 4))
    ```

2. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    print((-2 / 4), (2 / 4), (2 // 4), (-2 // 4))
    ```

3. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    print((2 % -4), (2 % 4), (2 ** 3 ** 2))
    ```

## Solución cuestionario

1. Pregunta 1:

    ```
    16 8.0 8
    ```
2. Pregunta 2:

    ```
    -0.5 0.5 0 -1
    ```
3. Pregunta 3:

    ```
    -2 2 512
    ```
