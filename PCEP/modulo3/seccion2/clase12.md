# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 2: Bucles en Python
## Clase: Resumen y cuestionario de la sección

### Resumen de sección

1. Existen dos tipos de bucles en Python: `while` y `for`:

    * El bucle `while` ejecuta una sentencia o un conjunto de sentencias siempre que una condición booleana especificada sea verdadera, por ejemplo:

    ```
    # Ejemplo 1
    while True:
        print("Atascado en un bucle infinito.")

    # Ejemplo 2
    counter = 5
    while counter > 2:
        print(counter)
        counter -= 1
    ```

    * El bucle `for` ejecuta un conjunto de sentencias muchas veces; se usa para iterar sobre una secuencia (por ejemplo, una lista, un diccionario, una tupla o un conjunto; pronto aprenderás sobre ellos) u otros objetos que son iterables (por ejemplo, cadenas). Puedes usar el bucle `for` para iterar sobre una secuencia de números usando la función incorporada `range()`. Mira los ejemplos a continuación:

    ```
    # Ejemplo 1
    word = "Python"
    for letter in word:
        print(letter, end="*")

    # Ejemplo 2
    for i in range(1, 10):
        if i % 2 == 0:
            print(i)
    ```

2. Puedes usar las sentencias `break` y `continue` para cambiar el flujo de un bucle:

    * Utiliza `break` para salir de un bucle, por ejemplo:

    ```
    text = "OpenEDG Python Institute"
    for letter in text:
        if letter == "P":
            break
        print(letter, end="")
    ```

    * Utiliza `continue` para omitir la iteración actual, y continuar con la siguiente iteración, por ejemplo:

    ```
    text = "pyxpyxpyx"
    for letter in text:
        if letter == "x":
            continue
        print(letter, end="")
    ```

3. Los bucles `while` y `for` también pueden tener una cláusula `else` en Python. La cláusula `else` se ejecuta después de que el bucle finalice su ejecución siempre y cuando no haya terminado con `break`, por ejemplo:

```
n = 0

while n != 3:
    print(n)
    n += 1
else:
    print(n, "else")

print()

for i in range(0, 3):
    print(i)
else:
    print(i, "else")
```

4. La función `range()` genera una secuencia de números. Acepta enteros y devuelve objetos de rango. La sintaxis de `range()` tiene el siguiente aspecto: range`(start, stop, step)`, donde:

    * `start` es un parámetro opcional que especifica el número de inicio de la secuencia (0 por defecto).
    * `stop` es un parámetro opcional que especifica el final de la secuencia generada (no está incluido).
    * `step` es un parámetro opcional que especifica la diferencia entre los números en la secuencia (1 por defecto).

Código de ejemplo:

```
for i in range(3):
    print(i, end=" ")  # Salidas: 0 1 2

for i in range(6, 1, -2):
    print(i, end=" ")  # Salidas: 6, 4, 2
```

### Cuestionario de sección

1. Crea un bucle `for` que cuente de 0 a 10, e imprima números impares en la pantalla. Usa el esqueleto de abajo: 

    ```
    for i in range(1, 11):
    # Línea de código.
        # Línea de código.
    ```

2. Crea un bucle `while` que cuente de 0 a 10, e imprima números impares en la pantalla. Usa el esqueleto de abajo:

    ```
    x = 1
    while x < 11:
        # Línea de código.
            # Línea de código.
        # Línea de código.   
    ```

3. Crea un programa con un bucle `for` y una sentencia `break`. El programa debe iterar sobre los caracteres en una dirección de correo electrónico, salir del bucle cuando llegue al símbolo `@` e imprimir la parte antes de `@` en una línea. Usa el esqueleto de abajo: 
    
    ```
    for ch in "john.smith@pythoninstitute.org":
        if ch == "@":
            # Línea de código.
        # Línea de código.
    ```

4. Crea un programa con un bucle `for` y una sentencia `continue`. El programa debe iterar sobre una cadena de dígitos, reemplazar cada `0` con `x`, e imprimir la cadena modificada en la pantalla. Usa el esqueleto de abajo:

    ```
    for digit in "0165031806510":
        if digit == "0":
            # Línea de código.
            # Línea de código.
        # Línea de código.    
    ```

5. ¿Cuál es la salida del siguiente código?

    ```
    n = 3

    while n > 0:
        print(n + 1)
        n -= 1
    else:
        print(n)
    ```

6. ¿Cuál es la salida del siguiente código?

    ```
    n = range(4)

    for num in n:
        print(num - 1)
    else:
        print(num)
    ```

7. ¿Cuál es la salida del siguiente código?

    ```
    for i in range(0, 6, 3):
        print(i)
    ```

### Solución cuestionario

1. Pregunta 1:

```
for i in range(0, 11):
    if i % 2 != 0:
        print(i)
```

2. Pregunta 2:

```
x = 1
while x < 11:
    if x % 2 != 0:
        print(x)
    x += 1
```

3. Pregunta 3:

```
for ch in "john.smith@pythoninstitute.org":
    if ch == "@":
        break
    print(ch, end="")
```

4. Pregunta 4:

```
for digit in "0165031806510":
    if digit == "0":
        print("x", end="")
        continue
    print(digit, end="")
```

5. Pregunta 5:

```
4
3
2
0
```
6. Pregunta 6:

```
-1
0
1
2
3
```

7. Pregunta 7:

```
0
3
```