# Prueba intermedia

1. El entrar al bloque `try:` implica que:

    * Ninguna de las instrucciones de este bloque se ejecuten
    * Todas las instrucciones de este bloque se ejecuten
    * El bloque será omitido
    * Algunas de las instrucciones de este bloque no se ejecuten

2. El bloque `except:` sin nombre:

    * Se puede colocar en cualquier lugar
    * No se puede utilizar si se ha utilizado algún bloque con nombre
    * Debe ser el primero
    * Debe ser el último

3. La excepción base en Python se llama:

    * `TopException`
    * `Exception`
    * `PythonException`
    * `BaseException`

4. La siguiente sentencia:
    ```
    assert var == 0
    ```

    * Es errónea
    * Detendrá el programa cuando `var != 0`
    * Detendrá el programa cuando `var == 0`
    * No tiene efecto

5. ¿Cuál es el resultado esperado del siguiente código?

    ```
    try:
        print("5"/0)
    except ArithmeticError:
        print("arit")
    except ZeroDivisionError:
        print("cero")
    except:
        print("algo")
    ```

    * cero
    * arit
    * algo
    * 0

6. ¿Cuáles de las siguientes son ejemplos de excepciones integradas concretas de Python? (Selecciona dos respuestas)

    * `ArithmeticError`
    * `IndexError`
    * `BaseException`
    * `ImportError`

7. ASCII es:

    * El nombre de un carácter
    * La abreviatura de American Standard Code for Information Interchange
    * El nombre de un Módulo Estándar de Python
    * El nombre de una variable predefinida de Python

8. UTF‑8 es:

    * La novena versión del estándar UTF
    * Un sinónimo para la palabra byte
    * Una forma de codificar puntos de código Unicode
    * El nombre de una versión de Python

9. UNICODE es un estándar:

    * Empleado por programadores en universidades
    * Como ASCII, pero mucho más expansivo
    * Honrado por todo el universo
    * Para codificar números punto flotante

10. El siguiente código imprime:

    ```
    x = '\''
    print(len(x))
    ```

    * 2
    * 3
    * 1
    * 20


11. El siguiente código imprime:
    ```
    print(ord('c') - ord('a'))
    ```
    * 1
    * 3
    * 2
    * 0

12. El siguiente código imprime:
    ```
    print(chr(ord('z') ‑ 2))
    ```

    * x
    * z
    * y
    * a

13. El siguiente código imprime:
    ```
    print(3 * 'abc' + 'xyz')
    ```
 
    * xyzxyzxyzxyz
    * abcxyzxyzxyz
    * abcabcabcxyz
    * bcabcxyzxyz

14. El siguiente código imprime:
    ```
    print('Mike' > "Mikey")
    ```

    * True
    * 0
    * 1
    * False

15. El siguiente código:
    ```
    print(float("1, 3"))
    ```
 
    * Imprime 13
    * Imprime 1,3
    * Genera una excepción ValueError
    * Imprime 1.3