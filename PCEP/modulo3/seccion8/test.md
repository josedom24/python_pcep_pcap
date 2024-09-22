# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 8: Prueba del Módulo


### Resumen del módulo

Aquí hay un breve resumen de los objetivos que has cubierto y con los que te has familiarizado en el Módulo 3:

* Valores booleanos para comparar diferentes valores y controlar las rutas de ejecución usando las instrucciones `if` y `if-else`;
* La utilización de bucles (`while` y `for`) y cómo controlar su comportamiento utilizando las instrucciones `break` y `continue`;
* La diferencia entre operaciones lógicas y bit a bit;
* El concepto de listas y procesamiento de listas, incluyendo la iteración proporcionada por el bucle `for`, y las rebanadas;
* La idea de los arreglos multidimensionales.

### Cuestionario módulo 3

La siguiente prueba se basa en lo que acabas de aprender. Hay 20 preguntas en total y debes obtener al menos un 70 % para aprobar.

1. Un operador que puede verificar si dos valores son iguales se codifica como:

    * `=`
    * `!=`
    * `==`
    * `===`

2. El valor asignado finalmente a x es igual a:

    ```
    x = 1
    x = x == x 
    ```

    * False
    * 0
    * 1
    * True

3. ¿Cuántos (`*`) enviará el siguiente fragmento de código a la consola?

    ```
    i = 0
    while i <= 3 :
        i += 2
        print("*")
    ```

    * 2
    * 3
    * 0
    * 1

4. ¿Cuántos (`*`) enviará el siguiente fragmento de código a la consola?

    ```
     i = 0
    while i <= 5 :
        i += 1
        if i % 2 == 0:
            break
        print("*") 
    ```

    * 0
    * 2
    * 1
    * 3

5. ¿Cuántos (`#`) enviará el siguiente fragmento de código a la consola?

    ```
    for i in range(1):
        print("#")
    else:
        print("#")
    ```

    * 2
    * 1
    * 0
    * 3

6. ¿Cuántos (`#`) enviará el siguiente fragmento de código a la consola?

    ```
    var = 0
    while var < 6:
        var += 1
        if var % 2 == 0:
            continue
        print("#")
    ```

    * 2
    * 3
    * 0
    * 1

7. ¿Cuántos (`#`) enviará el siguiente fragmento de código a la consola?

    ```
    var = 1
    while var < 10:
        print("#")
        var = var << 1

    ```

    * 2
    * 8
    * 1
    * 4

8. ¿Qué valor será asignado a la variable `x`?

    ```
    z = 10
    y = 0
    x = y < z and z > y or y > z and z < y 
    ```

    * 0
    * 1
    * True
    * False

9. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    a = 1
    b = 0
    c = a & b
    d = a | b
    e = a ^ b
    
    print(c + d + e) 
    ```

    * 3
    * 0
    * 2
    * 1

10. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list = [3, 1, -2]
    print(my_list[my_list[-1]])
    ```

    * 1
    * 3
    * -2
    * -1

11. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list = [1, 2, 3, 4]
    print(my_list[-3:-2]) 
    ```

    * []
    * [2, 3, 4]
    * [2]
    * [2, 3]

12. La segunda asignación:

    ```
    vals = [0, 1, 2]
    vals[0], vals[2] = vals[2], vals[0] 
    ```

    * mantiene la lista igual
    * extiende la lista
    * invierte la lista
    * acorta la lista

13. Después de la ejecución del siguiente fragmento de código, la suma de todos los elementos `vals` será igual a:

    ```
    vals = [0, 1, 2]
    vals.insert(0, 1)
    del vals[1] 
    ```

    * 2
    * 5
    * 4
    * 3

14. Observa el código, y selecciona las sentencias verdaderas: (Selecciona dos respuestas)

    ```
    nums = [1, 2, 3]
    vals = nums
    del vals[1:2] 
    ```

    * [ ] `nums` es replicada y asignada a `vals`
    * [ ] `nums` y `vals` son de la misma longitud
    * [ ] `nums` es más larga que `vals`
    * [ ] `nums` y `vals` se refieren a la misma lista

15. ¿Cuáles de los siguientes enunciados son verdaderos? (Selecciona dos respuestas)

    ```
    nums = [1, 2, 3]
    vals = nums[-1:-2] 
    ```

    * [ ] `nums` y `vals` son de la misma longitud
    * [ ] `nums` y `vals` son dos listas diferentes
    * [ ] `vals` es más larga que `nums`
    * [ ] `nums` es más larga que `vals`

16. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list_1 = [1, 2, 3]
    my_list_2 = []
    for v in my_list_1:
        my_list_2.insert(0, v)
    print(my_list_2)
    ```

    * [1, 1, 1]
    * [1, 2, 3]
    * [3, 2, 1]
    * [3, 3, 3]

17. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list = [1, 2, 3]
    for v in range(len(my_list)):
        my_list.insert(1, my_list[v])
    print(my_list) 
    ```

    * [1, 1, 1, 1, 2, 3]
    * [3, 2, 1, 1, 2, 3]
    * [1, 2, 3, 1, 2, 3]
    * [1, 2, 3, 3, 2, 1]

18 .¿Cuántos elementos contiene la lista `my_list`?

    ```
    my_list = [i for i in range(-1, 2)]
    ```

    * 1
    * 2
    * 3
    * 4

19. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    t = [[3-i for i in range (3)] for j in range (3)]
    s = 0
    for i in range(3):
        s += t[i][i]
    print(s) 
    ```

    * 4
    * 7
    * 6
    * 2

20. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list = [[0, 1, 2, 3] for i in range(2)]
    print(my_list[2][0])
    ```
 
    * 2
    * 1
    * 0
    * el fragmento generará un error de ejecución
