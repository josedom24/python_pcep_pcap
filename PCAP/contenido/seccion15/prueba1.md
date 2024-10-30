# Prueba Final 1

1. Sabiendo que una función llamada `fun()` reside en un módulo llamado `mod`, y que fue importada usando la siguiente sentencia:

    ```
    from mod import fun
    ```

    Elige la forma correcta de invocar la función `fun()`:

    * `mod.fun()`
    * `mod:fun()`
    * `mod::fun()`
    * `fun()`

2. ¿Qué resultado aparecerá después de ejecutar el siguiente fragmento de código?

    ```
    import math
    print(dir(math))
    ```

    * El número de entidades que residen dentro del módulo `math`
    * Un mensaje de error
    * Una cadena que contiene el nombre completo del módulo
    * Una lista de todas las entidades que residen dentro del módulo `math`

3. El código bytecode compilado de Python se almacena en archivos con la extensión:

    * `.pc`
    * `.pyb`
    * `.py`
    * `.pyc`

4. Suponiendo que los siguientes tres archivos: `a.py`, `b.py`, y `c.py` residen en el mismo directorio, ¿cuál será la salida producida después de ejecutar el archivo `c.py`?

    ```
    # archivo a.py
    print("a", end='')

    # archivo b.py
    import a
    print("b", end='')

    # archivo c.py
    print("c", end='')
    import a
    import b
    ```

    * `bc`
    * `cba`
    * `cab`
    * `bac`

5. ¿Cuál será la salida del siguiente código, ubicado en el archivo `p.py`?

    ```
    print(__name__)
    ```

    * `__p.py__`
    * `__main__`
    * `main`
    * `p.py`

6. La siguiente sentencia:

    ```
    from a.b import c
    ```

    provoca la importación de:

    * La entidad `c` del módulo `b` del paquete `a`
    * La entidad `b` del módulo `a` del paquete `c`
    * La entidad `c` del módulo `a` del paquete `b`
    * La entidad `a` del módulo `b` del paquete `c`

7. Si hay más de un bloque `except` después de un `try`, podemos decir que:

    * Uno o más bloques `except` serán ejecutados
    * Exactamente un bloque `except` será ejecutado
    * No más de un bloque `except` será ejecutado
    * Ninguno de los bloques `except` será ejecutado

8. ¿Cuál es el resultado esperado del siguiente fragmento de código?

    ```
    try:
        raise Exception
    except BaseException:
        print("a")
    except Exception:
        print("b")
    except:
        print("c")
    ```

    * `b`
    * Un mensaje de error
    * `1`
    * `a`

9. La siguiente línea de código:

    ```
    for line in open('text.txt', 'rt'):
    ```

    * Es inválida porque `open` devuelve nada
    * Pudiera ser válida si `line` es una lista
    * Es válida porque `open` devuelve un objeto iterable
    * Es inválida porque `open` devuelve un objeto no iterable

10. ¿Cuál es el resultado esperado del siguiente fragmento de código?

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

    * `a`
    * `1`
    * `b`
    * El código provocará un error de sintaxis

11. La siguiente sentencia:

    ```
    assert var != 0
    ```

    * Detendrá el programa cuando `var == 0`
    * Es errónea
    * No tiene efecto
    * Detendrá el programa cuando `var != 0`

12. El siguiente código:

    ```
    x = "\\\\"
    print(len(x))
    ```

    * Imprimirá `1`
    * Imprimirá `3`
    * Causará un error
    * Imprimirá `2`

13. El siguiente código:

    ```
    x = "\\\"
    print(len(x))
    ```

    * Imprimirá `1`
    * Causará un error
    * Imprimirá `2`
    * Imprimirá `3`

14. El siguiente código:

    ```
    print(chr(ord('p') + 2))
    ```

    * Imprimirá `s`
    * Imprimirá `q`
    * Imprimirá `r`
    * Imprimirá `t`

15. El siguiente código:

    ```
    print(float("1.3"))
    ```

    * Imprimirá `1.3`
    * Imprimirá `13`
    * Generará una excepción `ValueError`
    * Imprimirá `1,3`

16. Si el constructor de la clase se declara de la siguiente manera:

    ```
    class Class:
        def __init__(self, val=0):
            pass
    ```

    ¿Cuál de las asignaciones es inválida?

    * `object = Class()`
    * `object = Class(1)`
    * `object = Class(1, 2)`
    * `object = Class(None)`

17. ¿Cuál es el resultado esperado del siguiente código?

    ```
    class A:
        def __init__(self, v=2):
            self.v = v

        def set(self, v=1):
            self.v += v
            return self.v

    a = A()
    b = a
    b.set()
    print(a.v)
    ```

    * 1
    * 3
    * 2
    * 0

18. ¿Cuál es el resultado esperado del siguiente código?

    ```
    class A:
        A = 1
        def __init__(self):
            self.a = 0

    print(hasattr(A, 'a'))
    ```

    * 1
    * True
    * 0
    * False

19. ¿Cuál es el resultado esperado del siguiente código?

    ```
    class A:
        pass

    class B(A):
        pass

    class C(B):
        pass

    print(issubclass(A, C))
    ```

    * El código generará una excepción
    * El código imprimirá 1
    * El código imprimirá True
    * El código imprimirá False

20. El flujo o stream `sys.stderr` normalmente se asocia con:

    * Un dispositivo nulo
    * La impresora
    * La pantalla
    * El teclado

21. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        def __init__(self, v):
            self.__a = v + 1

    a = A(0)
    print(a.__a)
    ```

    * El código imprimirá 1
    * El código imprimirá 2
    * El código imprimirá 0
    * El código generará una excepción `AttributeError`

22. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        def __init__(self):
            pass

    a = A(1)
    print(hasattr(a, 'A'))
    ```

    * El código imprimirá True
    * El código imprimirá 1
    * El código generará una excepción
    * El código imprimirá False

23. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class A:
        def a(self):
            print('a')

    class B:
        def a(self):
            print('b')

    class C(B, A):
        def c(self):
            self.a()

    o = C()
    o.c()
    ```

    * El código imprimirá `a`
    * El código generará una excepción
    * El código imprimirá `c`
    * El código imprimirá `b`

24. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    try:
        raise Exception(1, 2, 3)
    except Exception as e:
        print(len(e.args))
    ```

    * El código generará una excepción no controlada
    * El código imprimirá 3
    * El código imprimirá 2
    * El código imprimirá 1

25. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    def my_fun(n):
        s = '+'
        for i in range(n):
            s += s
            yield s

    for x in my_fun(2):
        print(x, end='')
    ```

    * El código imprimirá `++`
    * El código imprimirá `+`
    * El código imprimirá `+++`
    * El código imprimirá `++++++`

26. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    class I:
        def __init__(self):
            self.s = 'abc'
            self.i = 0

        def __iter__(self):
            return self

        def __next__(self):
            if self.i == len(self.s):
                raise StopIteration
            v = self.s[self.i]
            self.i += 1
            return v

    for x in I():
        print(x, end='')
    ```

    * El código imprimirá `012`
    * El código imprimirá `abc`
    * El código imprimirá `cba`
    * El código imprimirá `210`

27. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    def o(p):
        def q():
            return '*' * p
        return q

    r = o(1)
    s = o(2)
    print(r() + s())
    ```

    * El código imprimirá `*`
    * El código imprimirá `****`
    * El código imprimirá `***`
    * El código imprimirá `**`

28. Si `s` es un stream abierto en modo lectura, la siguiente línea:

    ```
    q = s.read(1)
    ```

    leerá:

    * Un buffer del stream
    * Un kilobyte del stream
    * Un carácter del stream
    * Una línea del stream

29. Suponiendo que la invocación `open()` se ha realizado correctamente, el siguiente fragmento de código:

    ```
    for x in open('file', 'rt'):
        print(x)
    ```

    será:

    * Provocará una excepción
    * Leerá todo el archivo en una sola vez
    * Leerá el archivo línea por línea
    * Leerá el archivo carácter por carácter

30. Si deseas llenar un arreglo de bytes con datos leídos de un stream, ¿qué método puedes usar?

    * El método `readbytes()`
    * El método `readinto()`
    * El método `readfrom()`
    * El método `read()`

31. ¿Cuál de los siguientes comandos usarías para verificar la versión de pip? (Selecciona dos respuestas)

    * [ ] `pip-version`
    * [ ] `pip version`
    * [ ] `pip --version`
    * [ ] `pip3 --version`

32. ¿Cuál comando pip usarías para desinstalar un paquete previamente instalado?

    * `pip uninstall nombre_del_paquete`
    * `pip --remove nombre_del_paquete`
    * `pip delete nombre_del_paquete`
    * `pip --uninstall nombre_del_paquete`

33. Observa el siguiente código:

    ```
    numbers = [0, 2, 7, 9, 10]
    # Inserta la línea de código aquí.
    print(list(foo))
    ```

    ¿Qué línea insertarías para que el programa produzca la salida esperada?

    ```
    [0, 4, 49, 81, 100]
    ```

    * `foo = lambda num: num * 2, numbers)`
    * `foo = filter(lambda num: num ** 2, numbers)`
    * `foo = lambda num: num ** 2, numbers`
    * `foo = map(lambda num: num ** 2, numbers)`

34. Observa el siguiente código:

    ```
    numbers = [i*i for i in range(5)]
    # Inserta la línea de código aquí.
    print(foo)
    ```

    ¿Qué línea insertarías para que el programa produzca la salida esperada?

    ```
    [1, 9]
    ```

    * `foo = list(filter(lambda x: x % 2, numbers))`
    * `foo = list(map(lambda x: x // 2, numbers))`
    * `foo = list(map(lambda x: x % 2, numbers))`
    * `foo = list(filter(lambda x: x / 2, numbers))`

35. Observa el código a continuación:

    ```
    import random

    #
    # Inserta las líneas de código aquí.
    #

    print(a, b, c)
    ```

    ¿Qué líneas de código insertarías para que sea posible que el programa genere la siguiente salida?

    ```
    6 82 0
    ```

    * A: 
    ```
    a = random.randrange(10, 100, 3)
    b = random.randint(0, 100)
    c = random.choice((0, 100, 3))
    ```
    * B:
    ```
    a = random.choice((0, 100, 3))
    b = random.randrange(10, 100, 3)
    c = random.randint(0, 100)
    ```
    * C:
    ```
    a = random.randint(0, 100)
    b = random.randrange(10, 100, 3)
    c = random.choice((0, 100, 3))
    ```
    * D:
    ```
    a = random.randint(0, 100)
    b = random.choice((0, 100, 3))
    c = random.randrange(10, 100, 3)
    ```

36. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import os

    os.mkdir('pictures')
    os.chdir('pictures')

    print(os.getcwd())
    ```

    * El código imprimirá la ruta al directorio creado
    * El código imprimirá el propietario del directorio creado
    * El código imprimirá el nombre del directorio creado
    * El código imprimirá el contenido del directorio creado

Aquí tienes las preguntas 37 a 40 en formato markdown:

37. ¿Qué información se puede leer usando la función `uname` proporcionada por el módulo `os`? (Selecciona dos respuestas)

    * Última fecha de inicio de sesión
    * Identificador de hardware
    * Nombre del sistema operativo
    * Ruta actual

38. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import datetime

    datetime_1 = datetime(2019, 11, 27, 11, 27, 22)
    datetime_2 = datetime(2019, 11, 27, 0, 0, 0)

    print(datetime_1 - datetime_2)
    ```

    * `0 days, 11:27:22`
    * `11:27:22`
    * `11 hours, 27 minutes, 22 seconds`
    * `0 days`

39. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import timedelta

    delta = timedelta(weeks=1, days=7, hours=11)
    print(delta * 2)
    ```

    * El código generará una excepción
    * `2 weeks, 14 days, 22 hours`
    * `28 days, 22:00:00`
    * `7 days, 22:00:00`

40. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import calendar

    calendar.setfirstweekday(calendar.SUNDAY)
    print(calendar.weekheader(3))
    ```

    * `Tu`
    * `Sun Mon Tue Wed Thu Fri Sat`
    * `Su Mo Tu We Th Fr Sa`
    * `Tue`
```