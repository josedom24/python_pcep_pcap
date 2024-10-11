# El bloque else en las instrucciones while y for

## El bucle while y la rama else

Ambos bucles `while` y `for`, tienen una característica interesante. Veamos el siguiente ejemplo:

```
i = 1
while i < 5:
    print(i)
    i += 1
else:
    print("else:", i)
```

* Los bucles también pueden tener la rama `else`, como los `if`.
* La rama `else` del bucle siempre se ejecuta una vez, independientemente de si el bucle ha entrado o no en su cuerpo.

Vamos a modificar el código para que no se ejecute el bucle:

```
i = 5
while i < 5:
    print(i)
    i += 1
else:
    print("else:", i)
```

La condición que se evalúa en el bucle `while` es `False` al principi, opero puedes verificar que la rama `else` también se ejecuta.

## El bucle for y la rama else

Los bucles `for` se comportan de manera un poco diferente. Veamos un ejemplo:

```
for i in range(5):
    print(i)
else:
    print("else:", i)
```

* En este caso la rama `else` se ejecuta siempre al final de la ejecución del bucle.
* La salida puede ser un poco sorprendente: la variable `i` conserva su último valor.


¿Qué ocurre si el bucle `for` no se ejecuta`? Vamos a modificar el código para evitar la ejecución del bucle:

```
i = 111
for i in range(2, 1):
    print(i)
else:
    print("else:", i)
```

* El cuerpo del bucle no se ejecutará aquí en absoluto. Nota: hemos asignado la variable `i` antes del bucle.
* Cuando el cuerpo del bucle no se ejecuta, la variable de control conserva el valor que tenía antes del bucle.
* Si la variable de control no existe antes de que comience el bucle, no existirá cuando la ejecución llegue a la rama `else`.

## Cuestionario

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

3. Crea un programa con un bucle `for` y una instrucción `break`. El programa debe iterar sobre los caracteres en una dirección de correo electrónico, salir del bucle cuando llegue al símbolo `@` e imprimir la parte antes de `@` en una línea. Usa el esqueleto de abajo: 
    
    ```
    for ch in "john.smith@pythoninstitute.org":
        if ch == "@":
            # Línea de código.
        # Línea de código.
    ```

4. Crea un programa con un bucle `for` y una instrucción `continue`. El programa debe iterar sobre una cadena de dígitos, reemplazar cada `0` con `x`, e imprimir la cadena modificada en la pantalla. Usa el esqueleto de abajo:

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

## Solución cuestionario

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