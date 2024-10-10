# Prueba intermedia

La siguiente prueba se basa en lo que acabas de aprender. Hay 22 preguntas en total y debes obtener al menos un 70 % para aprobar.

1. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(x):
        if x % 2 == 0:
            return 1
        else:
            return
 
    print(fun(fun(2)) + 1)
    ```

    * None
    * 2
    * El código provocará un error de tiempo de ejecución
    * 1

2. El siguiente fragmento de código:

    ```
    def func(a, b):
        return a ** a
    
    
    print(func(2))
    ```

    * Dará como salida 4
    * Es erróneo
    * Dará como salida 2
    * Devolverá None

3. ¿Cuál es la salida del siguiente código?

    ```
    try:
        value = input("Ingresa un valor: ")
        print(value/value)
    except ValueError:
        print("Entrada incorrecta...")
    except ZeroDivisionError:
        print("Entrada errónea...")
    except TypeError:
        print("Entrada muy errónea...")
    except:
        print("¡Buuu!")
    ```

    * Entrada errónea...
    * ¡Buuu!
    * Entrada muy errónea...
    * Entrada incorrecta...

4. ¿Cuál es la salida del siguiente código?

    ```
    dictionary = {'one': 'two', 'three': 'one', 'two': 'three'}
    v = dictionary['one']
    
    for k in range(len(dictionary)):
        v = dictionary[v]
    
    print(v)
    ```

    * ('one', 'two', 'three')
    * two
    * one
    * three

5. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def any():
        print(var + 1, end='')
    
    
    var = 1
    any()
    print(var)
    ```

    * 12
    * 21
    * 11
    * 22

6. Una función integrada es una función que:

    * Tiene que ser importado antes de su uso
    * Viene con Python, y es una parte integral de Python
    * Está oculto a los programadores
    * Ha sido colocado dentro de tu código por otro programador

7. ¿Qué código insertarías en lugar del comentario para obtener el resultado esperado?

    Salida esperada:

    ```
    a
    b
    c
    ```

    ```
    dictionary = {}
    my_list = ['a', 'b', 'c', 'd']
    
    for i in range(len(my_list) - 1):
        dictionary[my_list[i]] = (my_list[i], )
    
    for i in sorted(dictionary.keys()):
        k = dictionary[i]
        # Inserta tu código aquí.
    ```

    * `print(k["0"])`
    * `print(k)`
    * `print(k['0'])`
    * `print(k[0])`

8. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(x):
        global y
        y = x * x
        return y
    
    
    fun(2)
    print(y)
    ```

    * 4
    * 2
    * El código provocará un error de tiempo de ejecución
    * Ninguno

9. ¿Cuál de las siguientes líneas inicia correctamente una definición de función sin parámetros?

    * `fun function():`
    * `def fun:`
    * `function fun():`
    * `def fun():`

10. El hecho de que las tuplas pertenezcan a tipos de secuencia significa que:

    * Se pueden modificar usando la instrucción del
    * Se pueden indexar y rebanar como las listas
    * Se pueden extender usando el método .append()
    * En realidad son listas

11. Asumiendo que my_tuple es una tupla creada correctamente, el hecho de que las tuplas son inmutables significa que la siguiente instrucción:

    ```
    my_tuple[1] = my_tuple[1] + my_tuple[0]
    ```

    * Es completamente correcta
    * Puede ser ejecutada solo si la tupla contiene al menos dos elementos
    * Es ilegal
    * Puede ser ilegal si la tupla contiene cadenas

12. El siguiente fragmento de código:

    ```
    def func(a, b):
        return a ** a
    
    
    print(func(2))
    ```
    
    * Dará como salida 4
    * Es erróneo
    * Dará como salida 2
    * Devolverá None

13. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    my_list = ['Mary', 'had', 'a', 'little', 'lamb']
    
    
    def my_list(my_list):
        del my_list[3]
        my_list[3] = 'ram'
    
    
    print(my_list(my_list))
    ``` 
    * no hay salida, el fragmento es erróneo
    * `['Mary', 'had', 'a', 'little', 'lamb']`
    * `['Mary', 'had', 'a', 'lamb']`
    * `['Mary', 'had', 'a', 'ram']`

14. ¿Cuál de las siguientes líneas inicia correctamente una función utilizando dos parámetros, ambos con valores predeterminados de cero?

    * `fun fun(a, b=0):`
    * `fun fun(a=0, b):`
    * `def fun(a=b=0):`
    * `def fun(a=0, b=0):`

15. Selecciona las sentencia verdadera sobre el bloque `try-except` en relación con el siguiente ejemplo. (Selecciona dos respuestas).

    ```
    try:
        # Algo de código...
    except:
        # Algo de código...
    ```

    * [ ] Si sospechas que un fragmento de código puede generar una excepción, se debe colocar dentro del bloque `try`.
    * [ ] Si existe un error de sintaxis en el código ubicado en el bloque `try`, la instrucción `except` no lo manejará, y una excepción `SyntaxError` será generada.
    * [ ] El código que sigue a la instrucción `try` será ejecutado si el código dentro de la instrucción `except` se encuentra con un error.
    * [ ] El código que sigue a la instrucción `except` será ejecutado si el código en el bloque `try` se encuentra con un error.

16. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(x, y, z):
        return x + 2 * y + 3 * z
    
 
    print(fun(0, z=1, y=3))
    ```

    * 3
    * El código es erróneo
    * 0
    * 9

17. Una función definida de la siguiente manera:  (Elegir dos respuestas)

    ```
    def function(x=0):
        return x
    ```

    * Debe invocarse sin ningún argumento.
    * Puede ser invocada sin ningún argumento.
    * Debe ser invocada con exactamente un argumento.
    * Puede ser invocado con exactamente un argumento.

18. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(inp=2, out=3):
        return inp * out
    
    
    print(fun(out=2))
    ```
    
    * 2
    * 4
    * El código es erróneo
    * 6

19. ¿Cuáles de las siguientes afirmaciones son verdaderas? (Selecciona dos respuestas)
    
    * [ ] El valor None puede ser empleado como argumento de operaciones aritméticas
    * [ ] El valor None no puede ser empleado fuera de las funciones
    * [ ] El valor None puede ser comparado con otras variables
    * [ ] El valor None puede ser asignado a variables

20. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def f(x):
        if x == 0:
            return 0
        return x + f(x - 1)
    
    
    print(f(3))
    ```

    * 1
    * 3
    * El código es erróneo
    * 6

21. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(x):
        x += 1
        return x
    
    
    x = 2
    x = fun(x + 1)
    print(x)
    ```

    * 3
    * 4
    * El código es erróneo
    * 5

22. ¿Cuál es la salida del siguiente código?

    ```
    tup = (1, 2, 4, 8)
    tup = tup[1:-1]
    tup = tup[0]
    print(tup)
    ```

    * (2)
    * El código es erróneo
    * (2, )
    * 2