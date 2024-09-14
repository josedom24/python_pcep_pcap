# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 2: Bucles en Python
## Clase: Bucle for

### Bucles en tu código con for

Otro tipo de bucle disponible en Python nos permite indicar la cantidad de iteraciones que va a dar nuestro bucle, en vez de verificar las condiciones.

Imagina que el cuerpo de un bucle debe ejecutarse exactamente cien veces. Si deseas utilizar el bucle `while` para hacerlo, puede tener este aspecto:

```
i = 0
while i < 100:
    # do_something()
    i += 1
```

Pero en este caso, que sabemos de antemano cuantas vueltas tiene que dar el bucle podemos usar la instrucción `for`.
En realidad, el bucle `for` está diseñado para realizar tareas más complicadas, puede "explorar" grandes colecciones de datos elemento por elemento. Te mostraremos como hacerlo pronto, pero ahora presentaremos una variante más sencilla de su aplicación.

Echa un vistazo al fragmento:

```
for i in range(100):
    # do_something()
    pass
```

Existen algunos elementos nuevos. Déjanos contarte sobre ellos:

* La palabra reservada `for` abre el bucle for. No existe ninguna condición, no tienes que pensar en las condiciones, ya que se verifican internamente, sin ninguna intervención.
* Cualquier **variable** después de la palabra reservada `for` es la **variable de control del bucle**; cuenta los giros del bucle y lo hace automáticamente.
* La palabra reservada `in` introduce un elemento de sintaxis que describe el **rango de valores posibles** que se asignan a la variable de control.
* La función `range()` (esta es una función muy especial) es responsable de generar todos los valores deseados de la variable de control; en nuestro ejemplo, la función creará (incluso podemos decir que alimentará el bucle con) valores en el conjunto : 0, 1, 2 .. 97, 98, 99; La función `range()` comienza su trabajo desde 0 y lo finaliza en un **numero anterior** al indicado como argumento.
* Nota la palabra clave `pass` dentro del cuerpo del bucle, no hace nada en absoluto; es una instrucción vacía : la colocamos aquí porque la sintaxis del bucle `for` exige al menos una instrucción dentro del cuerpo.

Veamos otro ejemplo. Echa un vistazo al fragmento de abajo. ¿Puedes predecir su salida?

```
for i in range(10):
    print("El valor de i es actualmente", i)
```

Ejecuta el código para verificar si tenías razón.

* El bucle se ha ejecutado diez veces (es el argumento de la función `range()`).
* El valor de la última variable de control es 9 (no 10, ya que comienza desde 0 , no desde 1).

La invocación de la función `range()` puede estar equipada con dos argumentos, no solo uno:

```
for i in range(2, 8):
    print("El valor de i es actualmente", i)
```

En este caso:

* El primer argumento determina el valor inicial (primero) de la variable de control.
* El último argumento muestra el primer valor que no se asignará a la variable de control.

Nota: la función `range()` solo acepta enteros como argumentos y genera secuencias de enteros.

¿Puedes adivinar la salida del programa? Ejecútalo para comprobar si ahora también estabas en lo cierto.

* El primer valor mostrado es 2 (tomado del primer argumento de `range()`).
* El último es 7 (aunque el segundo argumento de `range()` es 8).

### Más sobre el bucle for y la función range() con tres argumentos

La función `range()` también puede aceptar tres argumentos. Veamos el siguiente ejemplo:

```
for i in range(2, 8, 3):
    print("El valor de i es actualmente", i)
```

El tercer argumento es un **incremento**: es un valor agregado para controlar la variable en cada giro del bucle (como puedes sospechar, el valor predeterminado del incremento es 1).

¿Puedes decirnos cuántas líneas aparecerán en la consola y qué valores contendrán?

Ejecuta el programa para averiguar si tenías razón.

Deberías poder ver las siguientes líneas en la ventana de la consola:

```
El valor de i es actualmente 2
El valor de i es actualmente 5
```


¿Sabes por qué?:

* El primer argumento pasado a la función `range()` nos dice cual es el número de inicio de la secuencia (por lo tanto, 2 en la salida). 
* El segundo argumento le dice a la función dónde detener la secuencia (la función genera números hasta el número indicado por el segundo argumento, pero no lo incluye). 
* Finalmente, el tercer argumento indica el incremento, que en realidad significa la diferencia entre cada número en la secuencia de números generados por la función.

En nuestro caso:

1. **2** (número inicial)
2. **5** (2 incremento por 3 es igual a 5 - el número está dentro del rango de 2 a 8)
3. **8** (5 incremento por 3 es igual a 8 - el número no está dentro del rango de 2 a 8, porque el parámetro de parada no está incluido en la secuencia de números generados por la función).

Nota: si el conjunto generado por la función `range()` está vacío, el bucle no ejecutará su cuerpo en absoluto. Al igual que aquí, no habrá salida:

```
for i in range(1, 1):
    print("El valor de i es actualmente", i)
```

Nota: Si sólo usamos dos argumentos en la función `range()` (valor inical y valor final), el conjunto generado por `range()` debe ordenarse en un orden ascendente. No hay forma de forzar el `range()` para crear un conjunto en una forma diferente. Esto significa que el segundo argumento de `range()` debe ser mayor que el primero.

En este ejemplo, veremos que no hay ninguna salida:

```
for i in range(3, 1):
    print("El valor de i es actualmente", i)
```

Si queremos tener un orden descendente, tenemos que usar el tercer argumento de la función `range()` y utilizar un incremento negativo. Prueba el siguiente código:

```
for i in range(3, 1, -1):
    print("El valor de i es actualmente", i)
```

### Ejemplo: Cálculo de la potencia

Echemos un vistazo a un programa corto cuya tarea es escribir algunas de las primeras potencias de dos:

```
power = 1
for expo in range(16):
    print("2 a la potencia de", expo, "es", power)
    power *= 2
```

* La variable `expo` se utiliza como una variable de control para el bucle e indica el valor actual del exponente. 
* La propia exponenciación se sustituye multiplicando por dos. 
* Dado que 2<sup>0</sup> es igual a 1, después 2 × 1 es igual a 2<sup>1</sup>, 2 × 2<sup>1</sup> es igual a 2<sup>2</sup>, y así sucesivamente. 
