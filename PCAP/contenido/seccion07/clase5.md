# La instrucción `assert`

La instrucción `assert` es una herramienta útil en Python para garantizar que ciertas condiciones se cumplan en el código. Su sintaxis es:

```
assert expression
```

## Funcionamiento

1. **Evaluación de la expresión**: Se evalúa la expresión que sigue a la palabra clave `assert`.
2. **Condición verdadera**: Si la expresión se evalúa como `True`, o como un valor numérico distinto de cero, o como una cadena no vacía, o cualquier otro valor que no sea `None`, no ocurre nada.
3. **Condición falsa**: Si la expresión evalúa como `False`, se genera automáticamente una excepción llamada `AssertionError`.

## ¿Para qué podemos usar `assert`?

- **Verificación de condiciones**: Se utiliza en partes del código donde se necesita garantizar que los datos sean correctos, especialmente en funciones que podrían ser utilizadas por otras personas.
- **Prevención de errores**: La generación de una excepción `AssertionError` ayuda a asegurar que el código no produzca resultados no válidos y proporciona claridad sobre la naturaleza de la falla.
- **Suplemento a las excepciones**: Aunque las afirmaciones no reemplazan las excepciones ni validan los datos de forma completa, funcionan como un complemento. Se puede pensar en ellas como una "bolsa de aire" que protege el código en caso de que se presenten datos incorrectos.

A continuación se muestra un ejemplo de cómo utilizar `assert`:

```
import math

x = float(input("Ingresa un número: "))
assert x >= 0.0

x = math.sqrt(x)

print(x)
```

* Si el usuario ingresa un valor numérico válido mayor o igual a cero, el programa calculará y mostrará la raíz cuadrada de ese número.
* Si el usuario ingresa un valor negativo, el programa se detendrá y mostrará un mensaje de error similar a:

```
Traceback (most recent call last):
  File ".main.py", line 4, in <module>
    assert x >= 0.0
AssertionError
```

## Cuestionario

1. ¿Cuál es la salida esperada del siguiente código?
    ```
    try:
        print(1/0)
    except ZeroDivisionError:
        print("cero")
    except ArithmeticError:
        print("arit")
    except:
        print("algo")
    ```
2. ¿Cuál es la salida esperada del siguiente código?
    ```
    try:
        print(1/0)
    except ArithmeticError:
        print("arit")
    except ZeroDivisionError:
        print("cero")
    except:
        print("algo")
    ```
3. ¿Cuál es la salida esperada del siguiente código?
    ```
    def foo(x):
        assert x
        return 1/x


    try:
        print(foo(0))
    except ZeroDivisionError:
        print("cero")
    except:
        print("algo")
    ```

## Solución cuestionario

1. Pregunta 1

    `cero`

2. Pregunta 2

    `arit`

3. Pregunta 3

    `algo`