# Conversión entre cadenas y números

En muchas ocasiones, es necesario convertir números en cadenas o viceversa, especialmente cuando se procesan datos de entrada o salida. Python proporciona formas sencillas de realizar estas conversiones.

## De número a cadena: `str()`

Convertir un número (entero o flotante) a una cadena es muy fácil y siempre es posible mediante la función `str()`. Esto es útil cuando deseas manipular números como si fueran texto o concatenarlos con otras cadenas.

Ejemplo:

```
itg = 13
flt = 1.3
si = str(itg)
sf = str(flt)

print(si + ' ' + sf)
```

En este ejemplo, tanto el entero `itg` como el flotante `flt` se convierten en cadenas usando `str()`, permitiendo concatenarlos con un espacio entre ellos.

## De cadena a número: `int()` y `float()`

La conversión inversa, es decir, de una cadena a un número, solo es posible si la cadena representa un número válido. Si la cadena contiene caracteres no numéricos o un formato incorrecto, Python lanzará una excepción `ValueError`.

* **`int()`** se usa para convertir cadenas que representan números enteros.
* **`float()`** se usa para convertir cadenas que representan números con punto flotante.

Ejemplo:

```
si = '13'
sf = '1.3'
itg = int(si)
flt = float(sf)

print(itg + flt)
```

En este caso, las cadenas `'13'` y `'1.3'` se convierten en los números `13` (entero) y `1.3` (flotante), respectivamente. Luego, estos números se suman y el resultado se muestra en la consola.

## Cuestionario

1. ¿Cuál es la longitud de la siguiente cadena asumiendo que no hay espacios en blanco entre las comillas?
    ```
    """
    """
    ```

2. ¿Cuál es el resultado esperado del siguiente código?
    ```
    s = 'yesteryears'
    the_list = list(s)
    print(the_list[3:6])
    ```
3. ¿Cuál es el resultado esperado del siguiente código?
    ```
    for ch in "abc":
        print(chr(ord(ch) + 1), end='')
    ```

4. ¿Cuál es el resultado esperado del siguiente código?
    ```
    for ch in "abc123XYX":
        if ch.isupper():
            print(ch.lower(), end='')
        elif ch.islower():
            print(ch.upper(), end='')
        else:
            print(ch, end='')
    ```

5. ¿Cuál es el resultado esperado del siguiente código?
    ```
    s1 = '¿Dónde están las nevadas de antaño?'
    s2 = s1.split()
    print(s2[-2])
    ```

6. ¿Cuál es el resultado esperado del siguiente código?
    ```
    the_list = ['¿Dónde', 'están', 'las', 'nevadas?']
    s = '*'.join(the_list)
    print(s)
    ```

7. ¿Cuál es el resultado esperado del siguiente código?
    ```
    s = 'Es fácil o imposible'
    s = s.replace('fácil', 'difícil').replace('im', '')
    print(s)
    ```

8. ¿Cuál de las siguientes líneas describe una condición verdadera?
    ```
    'smith' > 'Smith'
    'Smiths' < 'Smith'
    'Smith' > '1000'
    '11' < '8'
    ```

9. ¿Cuál es el resultado esperado del siguiente código?
    ```
    s1 = '¿Dónde están las nevadas de antaño?'
    s2 = s1.split()
    s3 = sorted(s2)
    print(s3[1])
    ```

10. ¿Cuál es el resultado esperado del siguiente código?
    ```
    s1 = '12.8'
    i = int(s1)
    s2 = str(i)
    f = float(s2)
    print(s1 == s2)
    ```

## Solución cuestionario

1. Pregunta 1

    `1`

2. Pregunta 2

    `['t', 'e', 'r']`

3. Pregunta 3

    `bcd`

4. Pregunta 4

    `ABC123xyz`

5. Pregunta 5

    `de`

6. Pregunta 6

    `¿Dónde*están*las*nevadas?`

7. Pregunta 7

    `Es difícil o posible`

8. Pregunta 8

    1, 3 y 4

9. Pregunta 9

    `de`

10. Pregunta 10

    El código genera una excepción `ValueError`