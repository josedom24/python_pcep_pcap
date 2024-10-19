# Bucle for

## Estructura repetitiva for

Otro tipo de bucle disponible en Python nos permite indicar la cantidad de iteraciones que va a dar nuestro bucle, en vez de verificar las condiciones.

Imagina que el cuerpo de un bucle debe ejecutarse exactamente cien veces. Si deseas utilizar el bucle `while` para hacerlo, puede tener este aspecto:

```
i = 0
while i < 100:
    # do_something()
    i += 1
```

Pero en este caso, que **sabemos de antemano cuantas vueltas tiene que dar el bucle** podemos usar la instrucción `for`.
En realidad, el bucle `for` está diseñado para realizar tareas más complicadas: puede recorrer tipos de datos complejos como las secuencias (por ejemplo, una lista, un diccionario, una tupla o un conjunto; pronto aprenderás sobre ellos) u otros objetos que son iterables (por ejemplo las cadenas de caracteres). Pero ahora veremos una variante más simple de su aplicación:

```
for i in range(100):
    # do_something()
    pass
```

Existen algunos elementos nuevos. Déjanos contarte sobre ellos:

* La palabra reservada `for` abre el bucle for. No existe ninguna condición, no tienes que pensar en las condiciones, ya que se verifican internamente, sin ninguna intervención.
* Cualquier **variable** después de la palabra reservada `for` es la **variable de control del bucle**; cuenta los giros del bucle y lo hace automáticamente.
* La palabra reservada `in` introduce un elemento de sintaxis que describe el **rango de valores posibles** que se asignan a la variable de control.
* La función `range()` es responsable de generar todos los valores deseados de la variable de control; en nuestro ejemplo, la función creará  el conjunto : 0, 1, 2 .. 97, 98, 99; La función `range()` comienza su trabajo desde 0 y lo finaliza en un **numero anterior** al indicado como argumento.
* La palabra clave `pass` dentro del cuerpo del bucle, no hace nada en absoluto; es una instrucción vacía: la colocamos aquí porque la sintaxis del bucle `for` exige al menos una instrucción dentro del cuerpo.

Veamos otro ejemplo:

```
for i in range(10):
    print("El valor de i es actualmente:", i)
```

* El bucle se ha ejecutado diez veces (es el argumento de la función `range()`).
* El valor de la última variable de control es 9 (no 10, ya que comienza desde 0, no desde 1).

## renge() con dos argumentos

La invocación de la función `range()` puede estar equipada con dos argumentos, no solo uno:

```
for i in range(2, 8):
    print("El valor de i es actualmente:", i)
```

En este caso:

* El primer argumento determina el valor inicial (primero) de la variable de control.
* El último argumento muestra el primer valor que no se asignará a la variable de control.

La función `range()` solo acepta enteros como argumentos y genera secuencias de enteros.

En nuestro ejemplo:

* El primer valor mostrado es 2 (tomado del primer argumento de `range()`).
* El último es 7 (aunque el segundo argumento de `range()` es 8).

## range() con tres argumentos

La función `range()` también puede aceptar tres argumentos. Veamos el siguiente ejemplo:

```
for i in range(2, 8, 3):
    print("El valor de i es actualmente:", i)
```

El tercer argumento es un **incremento**: es un valor agregado para controlar la variable en cada giro del bucle (como puedes sospechar, el valor predeterminado del incremento es 1).

En este ejemplo, obtendremos la siguiente salida:
```
El valor de i es actualmente 2
El valor de i es actualmente 5
```

* El primer argumento pasado a la función `range()` nos dice cual es el número de inicio de la secuencia (por lo tanto, 2 en la salida). 
* El segundo argumento le dice a la función dónde detener la secuencia (la función genera números hasta el número indicado por el segundo argumento, pero no lo incluye). 
* Finalmente, el tercer argumento indica el incremento, que en realidad significa la diferencia entre cada número en la secuencia de números generados por la función.

En nuestro caso:

1. **2** (número inicial)
2. **5** (2 incremento por 3 es igual a 5 - el número está dentro del rango de 2 a 8)
3. **8** (5 incremento por 3 es igual a 8 - el número no está dentro del rango de 2 a 8, porque el parámetro de parada no está incluido en la secuencia de números generados por la función).

## Más sobre la función range()

Si el conjunto generado por la función `range()` está vacío, el bucle no ejecutará su cuerpo en absoluto. Al igual que aquí, no habrá salida:

```
for i in range(1, 1):
    print("El valor de i es actualmente:", i)
```

Si sólo usamos dos argumentos en la función `range()` (valor inicial y valor final), el conjunto generado por `range()` debe ordenarse en un orden ascendente. No hay forma de forzar el `range()` para crear un conjunto en una forma diferente. Esto significa que el segundo argumento de `range()` debe ser mayor que el primero.

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

## Ejemplo: Cálculo de la potencia

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


## Ejemplo: Recorrido de una cadena de caracteres

Como comentamos anteriormente el bucle for también nos permite recorrer tipos de datos que son iterables, es decir que podemos obtener el valor de cada elemento. Las **cadenas de caracteres son iterables** ya que podemos acceder a cada carácter que forma parte de la cadena. De esta forma usando un bucle `for` podemos imprimir los caracteres de una cadena:

```
cadena = "Python"
for caracter in cadena:
    print(caracter)
```

* El bucle recorre todos los caracteres de la cadena, por lo tanto en el ejemplo se dan 6 iteraciones.
* En cada iteración la variable `caracter` va tomando el valor de cada uno de los caracteres de la cadena.
* En este ejemplo lo imprimo en pantalla, pero podríamos hacer cualquier otra tarea.