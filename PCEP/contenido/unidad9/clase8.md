# El bloque else en las instrucciones while y for

## El bucle while y la rama else

Ambos bucles `while` y `for`, tienen una característica interesante (y rara vez se usa). Veamos el siguiente ejemplo:

```
i = 1
while i < 5:
    print(i)
    i += 1
else:
    print("else:", i)
```

* Los bucles también pueden tener la rama `else`, como los `if`.
* La rama `else` del bucle siempre se ejecuta una vez, independientemente de si el bucle ha entrado o no en su cuerpo.

¿Puedes adivinar la salida? Ejecuta el programa para comprobar si tenías razón.

Vamos a modificar el código para que no se ejecute el bucle:

```
i = 5
while i < 5:
    print(i)
    i += 1
else:
    print("else:", i)
```

La condición que se evalúa en el bucle `while` es `False` al principio. ¿Se ejecuta la rama `else`? Ejecuta y prueba el programa, y verifica si se ha ejecutado o no la rama `else`.

## El bucle for y la rama else

Los bucles `for` se comportan de manera un poco diferente. Veamos un ejemplo:

```
for i in range(5):
    print(i)
else:
    print("else:", i)
```

* En este caso la rama `else` se ejecuta siempre al final de la ejecución del bucle.
* La salida puede ser un poco sorprendente: la variable `i` conserva su último valor.


¿Qué ocurre si el bucle `for` no se ejecuta`? Vamos a modificar el código para evitar la ejecución del bucle:

```
i = 111
for i in range(2, 1):
    print(i)
else:
    print("else:", i)
```

¿Puedes adivinar la salida?

* El cuerpo del bucle no se ejecutará aquí en absoluto. Nota: hemos asignado la variable `i` antes del bucle.
* Cuando el cuerpo del bucle no se ejecuta, la variable de control conserva el valor que tenía antes del bucle.
* Si la variable de control no existe antes de que comience el bucle, no existirá cuando la ejecución llegue a la rama `else`.

