# Test intermedio

El siguiente test se basa en lo que acabas de aprender. Hay diez preguntas en total y debes obtener al menos un 70 % para aprobar.

1. Un operador capaz de comprobar si dos valores no son iguales se codifica como:

    * `not ==`
    * `!=`
    * `<>`

2. ¿Cuántos asteriscos enviará el siguiente fragmento a la consola?

    ```
    i = 2
    while i >= 0:
        print("*")
        i -= 2

    * Uno
    * Dos
    * Tres

3. ¿Cuántos `#` se enviarán a la consola?

    ```
    for i in range(-1,1):
        print("#")
    ```

    * Uno
    * Dos
    * Tres

4. ¿Qué valor se asignará a la variable x?

    ```
    z = 10
    y = 0
    x = z > y or z == y
    ```

    * `1`
    * `True`
    * `False`

5. ¿Cuál es la salida del siguiente código?

    ```
    my_list = [3, 1, -1]
    my_list[-1] = my_list[-2]
    print(my_list)
    ```

    * [1,1,-1]
    * [3,-1,1]
    * [3,1,1]

6. La segunda asignación del siguiente bloque de código...

    ```
    vals = [0, 1, 2]
    vals[0], vals[1] = vals[1], vals[2]
    ```

    * Acorta la lista
    * Extiende la lista
    * No cambia la longitud de la lista

7. Analiza el código y elige la frase verdadera.

    ```
    nums = []
    vals = nums
    vals.append(1)
    ```

    * `vals` es más largo que `nums`.
    * `nums` es más largo que `vals`.
    * `nums` y `vals` tienen la misma longitud.

8. Analiza el código y elige la frase verdadera.

   ```
    nums = []
    vals = nums[:]
    vals.append(1)
    ```

    * `nums` es más largo que `vals`.
    * `vals` es más largo que `nums`.
    * `nums` y `vals` tienen la misma longitud.


9. ¿Cuántos elementos contiene la lista `my_list`?

    ```
    my_list = [0 for i in range(1, 3)]
    ```

    * Uno
    * Dos
    * Tres

10. ¿Cuál es la salida del siguiente bloque de código?

    ```
    my_list = [0, 1, 2, 3]
    x = 1
    for elem in my_list:
        x *= elem
    print(x)
    ``

    * 0
    * 1
    * 6
