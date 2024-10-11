# Prueba Final

La Prueba Final se basa en lo que has aprendido en todo el curso. Hay 35 preguntas en total, y debes obtener al menos un 70% para aprobar. ¡Buena suerte!

1. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    my_list = [1, 2]
    
    for v in range(2):
        my_list.insert(-1, my_list[v])
    
    print(my_list)
    ```

    * `[1, 2, 1, 2]`
    * `[2, 1, 1, 2]`
    * `[1, 1, 1, 2]`
    * `[1, 2, 2, 2]`

2. El significado de un argumento posicional está determinado por:

    * Su valor
    * Su conexión con variables existentes
    * El nombre del argumento especificado junto con su valor
    * Su posición dentro de la lista de argumentos

3. ¿Cuáles de los siguientes enunciados son verdaderos respecto al código? (Selecciona dos respuestas)

    ```
    nums = [1, 2, 3]
    vals = nums
    ``` 

    * [ ] `vals` es más larga que `nums`
    * [ ] `nums` y `vals` son listas diferentes
    * [ ] `nums` y `vals` son diferentes nombres de la misma lista
    * [ ] `nums` tiene la misma longitud que `vals`

4. Un operador capaz de verificar si dos valores no son iguales se codifica como:

    * !=
    * <>
    * =/=
    * not ==

5. El siguiente fragmento de código:

    ```
    def function_1(a):
        return None
    
    
    def function_2(a):
        return function_1(a) * function_1(a)
    
    
    print(function_2(2))
    ```

    * Dará como salida 16
    * Dará como salida 4
    * Provocará un error de ejecución
    * Dará como salida 2

6. El resultado de la siguiente división:

    ```
    1 // 2
    ```

    * No se puede predecir
    * Es igual a 0.5
    * Es igual a 0
    * Es igual a 0.0

7. El siguiente fragmento de código:

    ```
    def func(a, b):
        return b ** a
    
    
    print(func(b=2, 2))
    ```

    * Es erróneo
    * Dará como salida 2
    * Dará como salida None
    * Dará como salida 4

8. ¿Qué valor se asignará a la variable x?

    ```
    z = 0
    y = 10
    x = y < z and z > y or y < z and z < y
    ```

    * 1
    * 0
    * False
    * True

9. ¿Cuáles de los siguientes nombres de variable son ilegales y provocarán una excepción de SyntaxError? (Selecciona dos respuestas)

    * [ ] for
    * [ ] in
    * [ ] print
    * [ ] In

10. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    my_list = [x * x for x in range(5)]
    
    
    def fun(lst):
        del lst[lst[2]]
        return lst
    
    
    print(fun(my_list))
    ```

    * `[0, 1, 4, 16]`
    * `[1, 4, 9, 16]`
    * `[0, 1, 9, 16]`
    * `[0, 1, 4, 9]`

11. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    x = 1
    y = 2
    x, y, z = x, x, y
    z, y, z = x, y, z
    
    print(x, y, z)
    ```

    * 1 2 2
    * 2 1 2
    * 1 2 1
    * 1 1 2

12. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    a = 1
    b = 0
    a = a ^ b
    b = a ^ b
    a = a ^ b
    
    print(a, b)
    ```

    * 1 1
    * 1 0
    * 0 1
    * 0 0

13. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    def fun(x):
        if x % 2 == 0:
            return 1
        else:
            return 2
    
    
    print(fun(fun(2)))
    ```

    * None
    * 2
    * El código provocará un error de ejecución
    * 1

14. Observa el fragmento de código y elige la sentencia verdadera:

    ```
    nums = [1, 2, 3]
    vals = nums
    del vals[:]
    ```

    * `nums` es más larga que `vals`
    * el código provocará un error de ejecución
    * `nums` y `vals` tienen la misma longitud
    * `vals` es más larga que `nums`

15. ¿Cuál es el resultado del siguiente fragmento de código si el usuario ingresa dos líneas que contienen 3 y 2 respectivamente?

    ```
    x = int(input())
    y = int(input())
    x = x % y
    x = x % y
    y = y % x
    print(y)
    ```

    * 3
    * 1
    * 2
    * 0

16. ¿Cuál es el resultado del siguiente fragmento de código si el usuario ingresa dos líneas que contienen 3 y 6 respectivamente?

    ```
    y = input()
    x = input()
    print(x + y)
    ```

    * 6
    * 3
    * 63
    * 36

17. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    print("a", "b", "c", sep="sep")
    ```

    * a b c
    * asepbsepc
    * abc
    * asepbsepcsep

18. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    x = 1 // 5 + 1 / 5
    print(x)
    ```

    * 0.2
    * 0
    * 0.5
    * 0.4

19. Suponiendo que `my_tuple` es una tupla creada correctamente, el hecho de que las tuplas sean inmutables significa que la siguiente instrucción:

    ```
    my_tuple[1] = my_tuple[1] + my_tuple[0]
    ```

    * Es ilegal
    * Es completamente correcta
    * Puede ser ilegal si la tupla contiene cadenas
    * Se puede ejecutar si y solo si la tupla contiene al menos dos elementos

20. ¿Cuál es el resultado del siguiente fragmento de código si el usuario ingresa dos líneas que contienen 2 y 4 respectivamente?

    ```
    x = float(input())
    y = float(input())
    print(y ** (1 / x))
    ```

    * 4.2
    * 0.0
    * 2.0
    * 1.0

21. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    dct = {'one': 'two', 'three': 'one', 'two': 'three'}
    v = dct['three']
    
    for k in range(len(dct)):
        v = dct[v]
    
    print(v)
    ```

    * `one`
    * `('one', 'two', 'three')`
    * `three`
    * `two`

22. ¿Cuántos elementos contiene la lista `lst`?

    ```
    lst = [i for i in range(-1, -2)]
    ```

    * Cero
    * Uno
    * Dos
    * Tres

23. ¿Cuáles de las siguientes líneas correctamente invocan la función definida a continuación? (Selecciona dos respuestas)

    ```
    def fun(a, b, c=0):
        # Cuerpo de la función.
    ```

    * `fun(0, 1, 2)`
    * `fun(b=0, a=0)`
    * `fun()`
    * `fun(b=1)`

24. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    def fun(x, y):
        if x == y:
            return x
        else:
            return fun(x, y-1)
    
    
    print(fun(0, 3))
    ```

    * 0
    * 2
    * El código provocará un error de ejecución
    * 1

25. ¿Cuántos (*) imprimirá el siguiente fragmento de código en la consola?

    ```
    i = 0
    while i < i + 2 :
        i += 1
        print("*")
    else:
        print("*")
    ```

    * 2
    * El fragmento entrará en un bucle infinito, imprimiendo un * por línea
    * 1
    * 0

26. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    tup = (1, 2, 4, 8)
    tup = tup[-2:-1]
    tup = tup[-1]
    print(tup)
    ```

    * 4
    * (4,)
    * (4)
    * 44

27. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    dd = {"1": "0", "0": "1"}
    for x in dd.vals():
        print(x, end="")
    ```

    * 0 1
    * El código es erróneo (el objeto dict no contiene el método vals())
    * 0 0
    * 1 0

28. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    dct = {}
    dct['1'] = (1, 2)
    dct['2'] = (2, 1)
    
    for x in dct.keys():
        print(dct[x][1], end="")
    ```

    * 21
    * 12
    * (1,2)
    * (2,1)

29. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    def fun(inp=2, out=3):
        return inp * out
    
    
    print(fun(out=2))
    ```

    * 4
    * 6
    * El fragmento de código es erróneo y provocará un SyntaxError
    * 2

30. ¿Cuántos (#) imprimirá el siguiente fragmento de código en la consola?

    ```
    lst = [[x for x in range(3)] for y in range(3)]
    
    for r in range(3):
        for c in range(3):
            if lst[r][c] % 2 != 0:
                print("#")
    ```

    * Seis
    * Nueve
    * Cero
    * Tres

31. ¿Cuál es el comportamiento esperado del siguiente programa si el usuario ingresa 0?

    ```
    try:
        value = input("Ingresa un valor: ")
        print(int(value)/len(value))
    except ValueError:
        print("Entrada incorrecta...")
    except ZeroDivisionError:
        print("Entrada erronea...")
    except TypeError:
        print("Entrada muy erronea...")
    except:
        print("¡Buuu!")
    ```

    * Entrada muy errónea...
    * 0.0
    * Entrada incorrecta...
    * Entrada errónea...
    * 1.0
    * ¡Buuu!

32. ¿Cuál es el comportamiento esperado del siguiente programa?

    ```
    try:
        print(5/0)
        break
    except:
        print("Lo siento, algo salió mal...")
    except (ValueError, ZeroDivisionError):
        print("Mala suerte...")
    ```

    * El programa provocará una excepción `SyntaxError`.
    * El programa generará una excepción y será manejada por el primer bloque `except`.
    * El programa provocará una excepción `ZeroDivisionError` y dará como salida el siguiente mensaje: Mala suerte...
    * El programa provocará una excepción `ValueError` y dará como salida un mensaje de error predeterminado.
    * El programa provocará una excepción `ZeroDivisionError` y dará como salida un mensaje de error predeterminado.
    * El programa provocará una excepción `ValueError` y dará como salida el siguiente mensaje: Mala suerte...

33. ¿Cuál es el comportamiento esperado del siguiente programa?

    ```
    foo = (1, 2, 3)
    foo.index(0)
    ```

    * El programa provocará una excepción `ValueError`.
    * El programa provocará una excepción `AttributeError`.
    * El programa provocará una excepción `TypeError`.
    * El programa provocará una excepción `SyntaxError`.
    * El programa dará como salida un 1 en la pantalla.

34. ¿Cuál de los siguientes fragmentos muestra la forma correcta de manejar múltiples excepciones en una sola cláusula `except`?

    ```
    # A:
    except (TypeError, ValueError, ZeroDivisionError):
        # Algo de código.
    
    # B:
    except TypeError, ValueError, ZeroDivisionError:
        # Algo de código.
    
    # C:
    except: (TypeError, ValueError, ZeroDivisionError)
        # Algo de código.
    
    # D:
    except: TypeError, ValueError, ZeroDivisionError
        # Algo de código.
    
    # E:
    except (TypeError, ValueError, ZeroDivisionError)
        # Algo de código.
    
    # F:
    except TypeError, ValueError, ZeroDivisionError
        # Algo de código.
    ```

    * A, C, y D
    * A solamente
    * F solamente
    * A y F
    * D y E
    * A y B
    * B y C

35. ¿Qué pasará cuando intentes ejecutar el siguiente código?

    ```
    print(¡Hola, Mundo!)
    ```

    * El código generará la excepción `AttributeError`.
    * El código generará la excepción `ValueError`.
    * El código imprimirá `¡Hola, Mundo!` en la consola.
    * El código generará la excepción `SyntaxError`.
    * El código generará la excepción `TypeError`.