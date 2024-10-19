# Excepciones en Python

Una excepción o un error de ejecución se produce durante la ejecución del programa. Las excepciones se puede manejar para que no termine el programa con un error no muy descriptivo para el usuario.

Para manejar las excepciones vamos a usar dos bloques:

```
try:
    ...
except:
    ...
```

* **try**: este es el lugar donde se coloca el código que se sospecha que puede causar un error o excepción. Aquí irán las instrucciones que pueden generar una excepción.
* **except**: esta parte fue diseñada para manejar la excepción. Estas instrucciones se ejecutan cuando se produce la excepción, podremos hacer varias cosas: mostrar un mensaje de error, cambiar el valor de una variable,...  Lo importante es que el programa no se detiene.

Como puedes ver, este enfoque acepta errores (los trata como una parte normal de la vida del programa) en lugar de intensificar los esfuerzos para evitarlos por completo.

## Ejemplo de tratamiento de excepción

Ahora nuestro ejemplo quedaría:

```
try:
    value = input('Ingresa un número natural: ')
    print('El recíproco de', value, 'es', 1/int(value))        
except:
    print('No se que hacer con', value)
```

Podemos resumir:

* Cualquier error que ocurra en las instrucciones en el bloque `try` no terminará la ejecución del programa. En cambio, el control saltará inmediatamente a la primera línea situada después de la palabra clave reservada `except`, y no se ejecutará ninguna otra línea del bloque `try`.
* El código en el bloque `except` se activa solo cuando se ha encontrado una excepción dentro del bloque `try`. No hay forma de llegar por ningún otro medio.
* Cuando el bloque `try` o `except` se ejecutan con éxito, el control continúa en la siguiente línea del programa de forma secuencial.

## Trabajar con varias excepciones

El programa anterior además de la excepción `ValueError` producida cuando introducimos un dato que no se puede convertir a entero, puede producir otro error si introducimos el 0, e intentamos dividir por él. En este caso se produce la excepción `ZeroDivisionError`.

Si tenemos posibilidad de varias excepciones, seguramente queremos tratar cada una de ellas de forma diferente, es decir ejecutar bloques `except` diferentes para cada una de ella.

En este caso el código quedaría:

```
try:
    value = input('Ingresa un número natural: ')
    print('El recíproco de', value, 'es', 1/int(value))        
except ValueError:
    print('No se que hacer con', value)    
except ZeroDivisionError:
    print('La división entre cero no está permitida en nuestro Universo.')  
```

* Hemos agregado un segundo `except`. 
* Cada `except` tiene el nombre de la excepción que va a tratar. 
* Sólo se va a ejecutar el `except` de la primera excepción que se produzca. Los demás bloques `excepts` no se ejecutarán.
* Podemos poner tantos bloques `excepts` como sean necesarios.

## El bloque except por defecto

En el ejemplo anterior hemos localizado dos posibles excepciones: `ValueError` y `ZeroDivisionError`, pero no podemos estar totalmente seguros que se pueda producir otra excepción. 

En este caso podemos indicar otro bloque `except` sin indicar ningún nombre de excepción, que habrá que colocar en último lugar, y que se ejecutará si la excepción provocada no es ninguna de las que estamos tratando. El código quedaría:

```
try:
    value = input('Ingresa un número natural: ')
    print('El recíproco de', value, 'es', 1/int(value))        
except ValueError:
    print('No se que hacer con', value)    
except ZeroDivisionError:
    print('La división entre cero no está permitida en nuestro Universo.')    
except:
    print('Ha sucedido algo extraño, ¡lo siento!')
```

## Ejemplos de excepción

* **ZeroDivisionError**: Se produce con cualquier operación (`/`, `//` o `%`) que intente dividir por 0.
* **ValueError**: Generalmente se produce cuando alguna función de conversión como `int()` o `float()` reciben valores que no pueden convertir.
* **TypeError**: Se produce cuando usas un dato de un tipo que no es el adecuado. Por ejemplo, los índices de las listas tienen que ser enteros:
    ```
    short_list = [1]
    one_value = short_list[0.5]
    ```
* **AttributeError**: Se produce cuando intentas usar un método que no existe para un dato:
    ```
    short_list = [1]
    short_list.append(2)
    short_list.depend(3)
    ```
* **SyntaxError**: Este tipo de error se producen cuando un error sintáctico o gramatical. No se suele manejar porque el programa no funciona con este tipo de errores.

## Cuestionario

1. ¿Cuál es la salida del siguiente programa si el usuario ingresa un 0?
    ```
    try:
        value = int(input("Ingresa un número entero: "))
        print(value/value)
    except ValueError:
        print("Entrada incorrecta...")
    except ZeroDivisionError:
        print("Entrada errónea...")
    except:
        print("¡Buuuu!")
    ```

## Solución cuestionario

1. Pregunta 1

    El programa dará como salida: `Entrada errónea...`.

