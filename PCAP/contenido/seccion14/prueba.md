# Prueba intermedia

1. ¿Qué palabra clave reservada usarías para definir una función anónima?

    * [ ] `lambda`
    * [ ] `afun`
    * [ ] `def`
    * [ ] `yield`

2. Selecciona las sentencias verdaderas. (Selecciona dos respuestas)

    * [ ] La función lambda puede evaluar sólo una expresión
    * [ ] La función lambda puede evaluar múltiples expresiones
    * [ ] La función lambda puede aceptar un máximo de dos argumentos
    * [ ] La función lambda puede aceptar cualquier número de argumentos

3. Observa el código a continuación:

    ```
    my_list = [1, 2, 3]
    # Insertar línea de código aquí.
    print(foo)
    ```

    ¿Qué fragmento insertarías para que el programa genere el siguiente resultado (tupla)?:

    ```
    (1, 4, 27)
    ```

    * [ ] `foo = tuple(map(lambda x: x*x, my_list))`
    * [ ] `foo = list(map(lambda x: x*x, my_list))`
    * [ ] `foo = tuple(map(lambda x: x**x, my_list))`
    * [ ] `foo = list(map(lambda x: x**x, my_list))`

4. Observa el código a continuación:

    ```
    my_tuple = (0, 1, 2, 3, 4, 5, 6)
    # Insertar línea de código aquí.
    print(foo)
    ```

    ¿Qué fragmento insertarías para que el programa genere el siguiente resultado (lista)?:

    ```
    [2, 3, 4, 5, 6]
    ```

    * [ ] `foo = tuple(filter(lambda x: x>1, my_tuple))`
    * [ ] `foo = tuple(filter(lambda x*0 and x*1, my_tuple))`
    * [ ] `foo = list(filter(lambda x==0 and x==1, my_tuple))`
    * [ ] `foo = list(filter(lambda x*0 and x*1, my_tuple))`

5. ¿Cuál es el resultado esperado de ejecutar el siguiente código?

    ```
    def I():
        s = 'abcdef'
        for c in s[::2]:
            yield c

    for x in I():
        print(x, end='')
    ```

    * [ ] Imprimirá `bdf`
    * [ ] Imprimirá `ace`
    * [ ] Imprimirá `abcdef`
    * [ ] Imprimirá una línea vacía.

6. ¿Cuál es el resultado esperado al ejecutar el siguiente código?

    ```
    def fun(n):
        s = '+'
        for i in range(n):
            s += s
            yield s

    for x in fun(2):
        print(x, end='')
    ```

    * [ ] Imprimirá +++
    * [ ] Imprimirá ++++++
    * [ ] Imprimirá ++
    * [ ] Imprimirá +

7. ¿Cuál es el resultado esperado de ejecutar el siguiente código?

    ```
    def o(p):
        def q():
            return '*' * p
        return q

    r = o(1)
    s = o(2)
    print(r() + s())
    ```

    * [ ] Imprimirá *
    * [ ] Imprimirá **
    * [ ] Imprimirá ****
    * [ ] Imprimirá ***

8. ¿Cuáles de los siguientes modos de apertura te permiten realizar operaciones de lectura? (Selecciona dos respuestas)

    * [ ] `w`
    * [ ] `a`
    * [ ] `r+`
    * [ ] `r`
9. ¿Cuál es el significado del valor representado por `errno.EEXIST`?

    * [ ] Número de archivo incorrecto
    * [ ] Archivo existente
    * [ ] Permiso denegado
    * [ ] Archivo inexistente

10. ¿Cuál es el resultado esperado del siguiente código?

    ```
    b = bytearray(3)
    print(b)
    ```

    * [ ] `bytearray(0, 0, 0)`
    * [ ] `3`
    * [ ] `bytearray(b'\x00\x00\x00')`
    * [ ] `bytearray(b'3')`

11. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import os

    os.mkdir('pictures')
    os.chdir('pictures')
    os.mkdir('thumbnails')
    os.chdir('thumbnails')
    os.mkdir('tmp')
    os.chdir('../')

    print(os.getcwd())
    ```

    * [ ] Imprimirá la ruta al directorio `tmp`
    * [ ] Imprimirá la ruta al directorio `root`
    * [ ] Imprimirá la ruta al directorio `thumbnails`
    * [ ] Imprimirá la ruta al directorio `pictures`

12. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import os

    os.mkdir('thumbnails')
    os.chdir('thumbnails')

    sizes = ['small', 'medium', 'large']

    for size in sizes:
        os.mkdir(size)

    print(os.listdir())
    ```

    * [ ] `['.', 'large', 'small', 'medium']`
    * [ ] `[]`
    * [ ] `['.', '..', 'large', 'small', 'medium']`
    * [ ] `['large', 'small', 'medium']`

13. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import date

    date_1 = date(1992, 1, 16)
    date_2 = date(1991, 2, 5)

    print(date_1 * date_2)
    ```

    * [ ] 345 days
    * [ ] 345 days, 0:00:00
    * [ ] 345, 0:00:00
    * [ ] 345

14. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from datetime import datetime

    datetime = datetime(2019, 11, 27, 11, 27, 22)
    print(datetime.strftime('%y/%B/%d %H:%M:%S'))
    ```

    * [ ] `19/November/27 11:27:22`
    * [ ] `2019/Nov/27 11:27:22`
    * [ ] `2019/11/27 11:27:22`
    * [ ] `19/11/27 11:27:22`

15. ¿Qué programa producirá la siguiente salida?:

    ```text
    Mo Tu We Th Fr Sa Su
    ```

    A:

    ```
    import calendar
    print(calendar.weekheader(2))
    ```

    B:

    ```
    import calendar
    print(calendar.weekheader())
    ```

    C:

    ```
    import calendar
    print(calendar.weekheader(3))
    ```

    D:

    ```
    import calendar
    print(calendar.week)
    ```

    * [ ] A
    * [ ] B
    * [ ] D
    * [ ] C

16. ¿Cuál es el resultado esperado del siguiente código?

    ```
    import calendar

    c = calendar.Calendar()

    for weekday in c.iterweekdays():
        print(weekday, end=" ")
    ```

    * [ ] `Mo Tu We Th Fr Sa Su`
    * [ ] `0 1 2 3 4 5 6`
    * [ ] `1 2 3 4 5 6 7`
    * [ ] `Su Mo Tu We Th Fr Sa`


