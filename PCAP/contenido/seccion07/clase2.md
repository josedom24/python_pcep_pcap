# Manejo de excepciones

La clave para manejar excepciones en Python está en la palabra reservada `try`. La estrategia para un manejo exitoso es:

1. **Intentar hacer algo** (`try`).
2. **Comprobar si todo salió bien**.

Aunque puede parecer más lógico verificar primero las circunstancias antes de realizar cualquier acción, como se muestra en el siguiente ejemplo:

```
first_number = int(input("Ingresa el primer número: "))
second_number = int(input("Ingresa el segundo número: "))

if second_number != 0:
    print(first_number / second_number)
else:
    print("Esta operación no puede ser realizada.")

print("FIN.")
```

Este enfoque, aunque comprensible, puede llevar a un código más extenso y menos legible. Python prefiere un enfoque más simple y eficiente, donde el manejo de errores ocurre directamente cuando algo sale mal, en lugar de revisar exhaustivamente todas las posibles circunstancias.

## Las instrucciones try-except

### El enfoque favorito de Python: `try` y `except`

El manejo de excepciones en Python sigue este enfoque preferido, utilizando las palabras clave `try` y `except`. A continuación, se detalla cómo funciona:

* **`try`**: Este bloque contiene el código que Python intentará ejecutar. Puede funcionar correctamente o generar una excepción.
* **`except`**: Si ocurre una excepción en el bloque `try`, Python salta a este bloque para manejar el error de manera adecuada.

### Ejemplo resumido:

```
try:
    # Código que puede fallar
except:
    # Código que maneja el fallo
```

1. Python ejecuta todas las instrucciones dentro del bloque `try`. Si todo sale bien, el flujo salta al final del bloque `except`, y el manejo de excepciones finaliza.
2. Si algo falla en el bloque `try`, Python interrumpe la ejecución de ese bloque y salta al bloque `except` para manejar el error. Esto puede hacer que algunas instrucciones dentro del `try` se omitan.

El uso de `try-except` permite manejar excepciones sin necesidad de comprobar manualmente cada situación, haciendo el código más legible y manejable.

Ejemplo:

```
try:
    print("1")
    x = 1 / 0
    print("2")
except:
    print("Oh cielos, algo salió mal...")

print("3")
```

## Manejando varias excepciones

El enfoque básico de manejo de excepciones con `try-except` tiene una desventaja significativa: cuando varias excepciones pueden ocurrir, un único bloque `except` no proporciona detalles específicos sobre lo que realmente salió mal.

Por ejemplo, considera el siguiente código:

```
try:
    x = int(input("Ingresa un número: "))
    y = 1 / x
except:
    print("Oh cielos, algo salió mal...")
```

El mensaje "Oh cielos, algo salió mal..." no ofrece información útil sobre la causa del fallo, pero en este caso hay dos posibles razones para la excepción:

1. El usuario ingresó datos no válidos que no pueden convertirse en un entero.
2. Se intentó dividir entre cero (cuando el usuario ingresó `0`).


Hay dos formas de abordar este problema:

1. **Usar bloques `try-except` consecutivos**: Cada uno maneja un tipo de excepción diferente. Este método es fácil, pero puede hacer que el código sea largo e innecesariamente complejo.
2. **Usar múltiples bloques `except`** para manejar diferentes excepciones dentro del mismo `try`:

```
try:
    x = int(input("Ingresa un número: "))
    y = 1 / x
except ValueError:
    print("Error: Datos no válidos, ingresa un número entero.")
except ZeroDivisionError:
    print("Error: No puedes dividir entre cero.")
except:
    print("Oh cielos, algo salió mal...")
```

* Si el bloque `try` genera una **excepción específica**, como `ValueError` o `ZeroDivisionError`, será manejada por el bloque correspondiente.
* Los bloques `except` son analizados en el mismo orden en que aparecen en el código.
* No debes usar más de un bloque de excepción con el mismo nombre.
* El número de diferentes bloques `except` es arbitrario, la única condición es que si se emplea el `try`, debes poner al menos un `except` (nombrado o no) después de el.
* La palabra clave reservada `except` no debe ser empleada sin que le preceda un `try`.
* Si uno de los bloques `except` es ejecutado, ningún otro lo será.
* Si ninguno de los bloques `except` especificados coincide con la excepción planteada, la excepción permanece sin manejar (lo discutiremos pronto).
* Si un `except` sin nombre existe, tiene que especificarse como el último.
* Si ocurre cualquier otra excepción no especificada, será manejada por el bloque genérico `except`.


Este método proporciona mayor control y permite manejar cada error de manera adecuada sin hacer crecer el código de forma innecesaria.



  
    
    
