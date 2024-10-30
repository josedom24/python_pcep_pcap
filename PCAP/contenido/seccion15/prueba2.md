# Prueba Final 2

1. ¿Cuál es el comportamiento esperado del siguiente fragmento de código?

    ```
    my_string = 'abcdef'

    def fun(s):
        del s[2]
        return s

    print(fun(my_string))
    ```

    * El programa provocará un error
    * El programa dará como salida `abdef`
    * El programa dará como salida `abcef`
    * El programa dará como salida `acdef`

2. ¿Cuántos (`*`) enviará el siguiente fragmento de código a la consola?

    ```
    i = 4

    while i > 0:
        i -= 2
        print("*")
        if i == 2:
            break
    else:
        print("*")
    ```

    * uno
    * dos
    * cero
    * El fragmento entrará en un bucle infinito, imprimiendo constantemente un `*` por línea

3. ¿Cuál es el comportamiento esperado del siguiente código?

    ```
    x = """
    """
    print(len(x))
    ```

    * El código dará como salida `1`
    * El código dará como salida `2`
    * El código dará como salida `3`
    * El código provocará un error

4. ¿Cuál es el comportamiento esperado del siguiente código?

    ```
    x = 16
    while x > 0:
        print('*', end='')
        x //= 2
    ```

    * El código dará como salida `*****`
    * El código dará como salida `***`
    * El código dará como salida `*`
    * El código entrará en un bucle infinito

5. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    class A:
        def __init__(self, name):
            self.name = name

    a = A("class")
    print(a)
    ```

    * Una cadena que termina con un número hexadecimal largo
    * Un número
    * `name`
    * `class`

6. ¿Cuál es el efecto esperado al ejecutar el siguiente código?

    ```
    class A:
        def __init__(self, v):
            self._a = v + 1

    a = A(0)
    print(a._a)
    ```

    * El código dará como salida `1`
    * El código dará como salida `2`
    * El código dará como salida `0`
    * El código generará una excepción `AttributeError`

7. Un directorio/carpeta de paquete puede contener un archivo destinado a inicializar el paquete. ¿Cuál es su nombre?

    * `__init__.py`
    * `init.py`
    * `__init__.`
    * `__init.py__`

8. Selecciona las sentencias **verdaderas**. (Seleccione **dos** respuestas)

    * [ ] El primer parámetro de un método de clase **no** tiene que ser llamado *self*
    * [ ] Si una clase contiene el método `__init__`, este **no puede** devolver un valor
    * [ ] El primer parámetro de un método de clase debe llamarse *self*
    * [ ] Si una clase contiene el método `__init__`, puede devolver un valor

9. ¿Qué valor se le asignará a la variable `x`?

    ```
    z = 2
    y = 1
    x = y < z or z > y and y > z or z < y
    ```

    * `True`
    * `False`
    * `1`
    * `0`

10. ¿Cuál es el resultado esperado del siguiente código?

    ```
    t = (1,)
    t = t[0] + t[0]
    print(t)
    ```

    * `2`
    * `(1, 1)`
    * `(1,)`
    * `1`

11. ¿Qué es **verdadero** sobre el siguiente fragmento de código?

    ```
    def fun(d, k, v):
        d[k] = v

    my_dictionary = {}
    print(fun(my_dictionary, '1', 'v'))
    ```

    * El código dará como salida `None`
    * El código dará como salida `v`
    * El código dará como salida `1`
    * El código es erróneo

12. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import datetime

    datetime = datetime(2019, 11, 27, 11, 27, 22)
    print(datetime.strftime('%Y/%m/%d %H:%M:%S'))
    ```

    * `2019/11/27 11:27:22`
    * `19/11/27 11:27:22`
    * `2019/Nov/27 11:27:22`
    * `2019/November/27 11:27:22`

13. ¿Cuál es el resultado esperado del siguiente código?

    ```
    def a(x):
        def b():
            return x + x
        return b

    x = a('x')
    y = a('')
    print(x() + y())
    ```

    * `xx`
    * `x`
    * `xxxx`
    * `xxxxxx`

14. ¿Qué es **verdadero** acerca de la siguiente línea de código?

    ```
    print(len((1, )))
    ```

    * El código dará como salida `1`
    * El código dará como salida `2`
    * El código dará como salida `0`
    * El código es erróneo

15. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import timedelta

    delta = timedelta(weeks=1, days=7, hours=11)
    print(delta)
    ```

    * `14 days, 11:00:00`
    * `7 days, 11:00:00`
    * `1 week, 7 days, 11 hours`
    * `2 weeks, 11:00:00`

16. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        pass

    class B:
        pass

    class C(A, B):
        pass

    print(issubclass(C, A) and issubclass(C, B))
    ```

    * El código imprimirá `True`
    * El código imprimirá `False`
    * El código imprimirá una línea vacía
    * El código generará una excepción

17. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        def a(self):
            print('a')

    class B:
        def a(self):
            print('b')

    class C(A, B):
        def c(self):
            self.a()

    o = C()
    o.c()
    ```

    * El código imprimirá `a`
    * El código imprimirá `b`
    * El código imprimirá `c`
    * El código generará una excepción

18. Sabiendo que la función llamada `f()` reside dentro del módulo llamado `m`, y el código contiene la siguiente sentencia `import`:

    ```
    from f import m
    ```

    Elige la forma correcta de invocar la función:

    * La función no se puede invocar porque la sentencia `import` es inválida
    * `mod:f()`
    * `mod.f()`
    * `f()`

19. ¿Cuál es el nombre del directorio/carpeta creado por Python que se usa para almacenar archivos `pyc`?

    * `__pycache__`
    * `__pyc__`
    * `__pycfiles__`
    * `__cache__`

20. ¿Cuál es el comportamiento esperado del siguiente código?

    ```
    d = {1: 0, 2: 1, 3: 2, 0: 1}
    x = 0

    for y in range(len(d)):
        x = d[x]

    print(x)
    ```

    * El código dará como salida `0`
    * El código dará como salida `2`
    * El código dará como salida `1`
    * El código provocará un error en tiempo de ejecución

21. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    d = {}
    d['2'] = [1, 2]
    d['1'] = [3, 4]

    for x in d.keys():
        print(d[x][1], end="")
    ```

    * `24`
    * `42`
    * `13`
    * `31`

22. ¿Cuáles de las siguientes funciones proporcionadas por el módulo `os` están disponibles tanto en Windows como en Unix? (Selecciona **dos** respuestas)

    * [ ] `mkdir()`
    * [ ] `chdir()`
    * [ ] `getgid()`
    * [ ] `getgroups()`

23. ¿Cuál es la salida esperada del siguiente código si el usuario ingresa dos líneas que contienen `1` y `2` respectivamente?

    ```
    y = input()
    x = input()
    print(x + y)
    ```

    * `21`
    * `12`
    * `3`
    * `2`

24. ¿Cuál es el comportamiento esperado del siguiente código?

    ```
    import os

    os.makedirs('pictures/thumbnails')
    os.rmdir('pictures')
    ```

    * El código generará un error
    * El código eliminará los directorios `pictures` y `thumbnails`
    * El código eliminará solamente el directorio `pictures`
    * El código eliminará solamente el directorio `thumbnails`

25. ¿Cuál es el resultado esperado del siguiente código?

    ```
    class A:
        A = 1
        def __init__(self, v=2):
            self.v = v + A.A
            A.A += 1

        def set(self, v):
            self.v += v
            A.A += 1
            return 

    a = A()
    a.set(2)
    print(a.v)
    ```

    * `5`
    * `3`
    * `1`
    * `7`

26. Si `s` es un stream abierto en modo lectura, la siguiente línea:

    ```
    q = s.readlines()
    ```

    Asignará a `q` como:

    * Una lista
    * Una cadena
    * Una tupla
    * Un diccionario

27. El significado de un *argumento de palabra clave* está determinado por:

    * El nombre del argumento especificado junto con su valor
    * Su posición dentro de la lista de argumentos
    * Su conexión con variables existentes
    * Su valor

28. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import calendar  

    c = calendar.Calendar(calendar.SUNDAY)

    for weekday in c.iterweekdays():
        print(weekday, end=" ")
    ```

    * `6 0 1 2 3 4 5`
    * `7 1 2 3 4 5 6`
    * `Su Mo Tu We Th Fr Sa`
    * `Su`

29. ¿Qué puedes hacer si deseas decirles a los usuarios de tu módulo que no se debe **acceder directamente** a una variable en particular?

    * Iniciar su nombre con `_` o `__`
    * Iniciar su nombre con una letra mayúscula
    * Construir su nombre solo con letras minúsculas
    * Usar su número en lugar de su nombre

30. Si deseas escribir el contenido de un arreglo de bytes en un stream, ¿qué método se puede usar?

    * `write()`
    * `writefrom()`
    * `writeto()`
    * `writebytearray()`


31. ¿Cuál de los siguientes enunciados es **verdadero** con respecto al siguiente fragmento de código?

    ```
    str_1 = 'string'
    str_2 = str_1[:]
    ```

    * `str_1` y `str_2` son cadenas diferentes (pero iguales)
    * `str_1` y `str_2` son diferentes nombres de la misma cadena
    * `str_1` es más larga que `str_2`
    * `str_2` es más larga que `str_1`

32. ¿Qué operador usarías para verificar si dos valores son **iguales**?

    * `==`
    * `===`
    * `>=`
    * `is`

33. Si hay un bloque `finally:` dentro de un `try:`, podemos decir que:

    * El código dentro del bloque `finally:` siempre será ejecutado
    * El código dentro del bloque `finally:` será ejecutado cuando no haya un bloque `else:`
    * El código dentro del bloque `finally:` no será ejecutado sino se genera una excepción
    * El código dentro del bloque `finally:` no será ejecutado si un bloque `except:` es ejecutado

34. La clase `Exception` contiene una propiedad llamada `args` - ¿Qué es?

    * Una tupla
    * Una cadena
    * Un diccionario
    * Una lista

35. Si el constructor de la clase se declara de la siguiente manera:

    ```
    class Class:
        def __init__(self):
            pass
    ```

    ¿Cuál de las asignaciones es **válida**?

    * `object = Class()`
    * `object = Class(1)`
    * `object = Class(None)`
    * `object = Class(1,2)`

36. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    try:
        raise Exception
    except BaseException:
        print("a", end='')
    else:
        print("b", end='')
    finally:
        print("c")
    ```

    * `ac`
    * `bc`
    * `ab`
    * `a`

37. ¿Cuál es el comportamiento esperado del siguiente código?

    ```
    x = "\\"
    print(len(x))
    ```

    * El código provocará un error
    * El código dará como salida `1`
    * El código dará como salida `2`
    * El código dará como salida `3`

38. ¿Qué es **verdadero** sobre el siguiente fragmento de código?

    ```
    def fun(par2, par1):
        return par2 + par1

    print(fun(par2=1, 2))
    ```

    * El código es erróneo
    * El código dará como salida `3`
    * El código dará como salida `2`
    * El código dará como salida `1`

39. ¿Cuál es el resultado esperado del siguiente código?

    ```
    v = 1 + 1 // 2 + 1 / 2 + 2
    print(v)
    ```

    * `3.5`
    * `4`
    * `4.0`
    * `3`

40. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        def __init__(self):
            pass

        def f(self):
            return 1

        def g():
            return self.f()

    a = A()
    print(a.g())
    ```

    * El código generará una excepción
    * El código dará como salida `0`
    * El código dará como salida `1`
    * El código dará como salida `True`

41. ¿Cuál es la salida esperada del siguiente código, ubicado en el archivo `module.py`?

    ```
    print(__name__)
    ```

    * `__main__`
    * `module.py`
    * `__module.py__`
    * `main`

42. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    class X:
        pass

    class Y(X):
        pass

    class Z(Y):
        pass

    x = X()
    z = Z()
    print(isinstance(x, Z), isinstance(z, X))
    ```

    * `True False`
    * `False True`
    * `False False`
    * `True True`

43. ¿Cuál es el resultado esperado del siguiente código?

    ```
    def fun(n):
        s = ''
        for i in range(n):
            s += '*'
            yield s

    for x in fun(3):
        print(x, end='')
    ```

    * `******`
    * `****`
    * `2***`
    * `*`

44. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    t = (1, 2, 3, 4)
    t = t[-2:-1]
    t = t[-1]
    print(t)
    ```

    * `3`
    * `(3)`
    * `(3,)`
    * `33`

45. ¿Cuál es el resultado esperado del siguiente código?

    ```
    a = True
    b = False
    a = a or b
    b = a and b
    a = a or b
    print(a, b)
    ```

    * `True False`
    * `True True`
    * `False False`
    * `False True`

46. ¿Cuál es el comportamiento esperado del siguiente fragmento de código?

    ```
    def fun(x):
        return 1 if x % 2 != 0 else 2

    print(fun(fun(1)))
    ```

    * El programa dará como salida `1`
    * El programa dará como salida `2`
    * El programa dará como salida `None`
    * El código provocará un error en tiempo de ejecución

47. ¿Cuántas líneas vacías enviará el siguiente fragmento a la consola?

    ```
    my_list = [[c for c in range(r)] for r in range(3)]

    for element in my_list:
        if len(element) < 2:
            print()
    ```

    * Dos
    * Una
    * Cero
    * Tres

48. ¿Cuál es el resultado esperado del siguiente código?

    ```
    my_string_1 = 'Bond'
    my_string_2 = 'James Bond'

    print(my_string_1.isalpha(), my_string_2.isalpha())
    ```

    * `True False`
    * `False True`
    * `True True`
    * `False False`

49. Selecciona las sentencias **verdaderas**. (Selecciona **dos** respuestas)

    * [ ] _PyPI_ es la abreviatura de Python Package Index
    * [ ] _PyPI_ es uno de los muchos repositorios existentes de Python
    * [ ] _PyPI_ es el único repositorio existente de Python
    * [ ] _PyPI_ es la abreviatura de Python Package Installer

50. ¿Cuál es el resultado esperado del siguiente código?

    ```
    class A:
        A = 1
        def __init__(self):
            self.a = 0

    print(hasattr(A, 'A'))
    ```

    * `True`
    * `0`
    * `1`
    * `False`


51. ¿Qué línea **correctamente** invoca la función definida a continuación?

    ```
    def fun(a, b, c=0):
        # cuerpo de la función
    ```

    * `fun(a=1, b=0, c=0)`
    * `fun(0)`
    * `fun(1, c=2)`
    * `fun(b=0, b=0)`

52. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    d = {'one': 1, 'three': 3, 'two': 2}

    for k in sorted(d.values()):
        print(k, end=' ')
    ```

    * `1 2 3`
    * `3 2 1`
    * `2 3 1`
    * `3 1 2`

53. ¿Qué es **verdadero** sobre el siguiente fragmento de código?

    ```
    print("a", "b", "c", sep="'")
    ```

    * El código dará como salida `a'b'c`
    * El código dará como salida `abc`
    * El código dará como salida `a b c`
    * El código es erróneo

54. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    print(len([i for i in range(0, -2)]))
    ```

    * `0`
    * `3`
    * `2`
    * `1`

55. ¿Qué es PEP 8?

    * Un documento que proporciona convenciones de codificación y una guía de estilo para el código Python
    * Un documento que describe el programa de desarrollo y lanzamiento de las versiones de Python
    * Un documento que describe una extensión del mecanismo de importación de Python que mejora el intercambio de archivos de código fuente de Python
    * Un documento que proporciona convenciones de codificación y una guía de estilo para el código C que comprende la implementación C de Python

56. ¿Cuál es el comportamiento esperado del siguiente fragmento de código?

    ```
    my_list = [1, 2, 3, 4]

    my_list = list(map(lambda x: 2*x, my_list))
    print(my_list)
    ```

    * El código dará como salida `2 4 6 8`
    * El código dará como salida `1 2 3 4`
    * El código dará como salida `10`
    * El código provocará un error en tiempo de ejecución

57. ¿Cuál es el comportamiento esperado del siguiente fragmento de código?

    ```
    try:
        raise Exception
    except:
        print("c")
    except BaseException:
        print("a")
    except Exception:
        print("b")
    ```

    * El código provocará un error
    * El código dará como salida `a`
    * El código dará como salida `b`
    * El código dará como salida `c`

58. ¿Cuál es el resultado esperado del siguiente código?

    ```
    x, y, z = 3, 2, 1
    z, y, x = x, y, z
    print(x, y, z)
    ```

    * `1 2 3`
    * `1 2 2`
    * `3 2 1`
    * `2 1 3`

59. ¿Con qué se asocia normalmente el stream `sys.stdout`?

    * La pantalla
    * El teclado
    * La impresora
    * Un dispositivo `null`

60. ¿Qué operación `pip` usarías para verificar qué paquetes de Python se han instalado hasta ahora?

    * `list`
    * `help`
    * `show`
    * `dir`


