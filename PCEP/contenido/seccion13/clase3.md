# Funciones parametrizadas

A una función le podemos pasar información. Dichos datos pueden modificar el comportamiento de la función, haciéndola más flexible y adaptable a condiciones cambiantes.

Los datos que pasamos a una función lo llamamos **parámetros** o **argumentos**.

* **Los parámetros son variables que solo existen dentro de las funciones en donde han sido definidos**, y el único lugar donde un parámetro puede ser definido es entre los paréntesis después del nombre de la función, donde se encuentra la palabra reservada `def`.
* La **asignación de un valor a un parámetro de una función** se hace en el momento en que llamamos a la función, especificando el **argumento** correspondiente.

Veamos un ejemplo. La siguiente función muestra el número enviado al parámetro:

```
def mensaje(numero):
    print("Has introducido el número:", numero)

mensaje(5)
```

* En este caso el parámetro se llama `numero`.
* Y el argumento es el dato que se indica en la llamada, en este ejemplo el número `5` (el argumento podría ser un literal, una variable o una expresión). 
* Cuando llamamos a la función, el parámetro `numero` tomara el valor del argumento, el `5`.
* El parámetro se inicializa cuando se llama a la función con el valor del argumento.

Recuerda que:

* **Los parámetros solo existen dentro de las funciones**..
* **Los argumentos existen fuera de las funciones**, y son los que pasan los valores a los parámetros correspondientes.

## Varios parámetros y argumentos

Si en una función se definen un número de parámetros determinado, al llamarla se deberá indicar es mismo número de argumentos. Sino lo hacemos se producirá un error.

Si ejecutamos el siguiente código:

```
def mensaje(numero):
    print("Has introducido el número:", numero)

mensaje()
```
Se producirá un error del tipo: `TypeError: mensaje() missing 1 required positional argument: 'numero'`

## Paso de parámetros en las funciones

El valor del argumento utilizado durante la invocación (en nuestro ejemplo, `5`) ha sido pasado a la función, dándole un valor inicial al parámetro con el nombre de `number`.
Es posible tener una variable con el mismo nombre del parámetro de la función.

El siguiente código muestra un ejemplo de esto:
```
def mensaje(numero):
    print("Ingresa un número:", numero)
numero = 1234
mensaje(5)
print(numero)
```

* En este caso hay una variable `numero` que existe fuera de la función (y no existe dentro de la función).
* Y un parámetro `numero` que existe dentro de la función y no existe fuera de la función.
* Una situación como la anterior, activa un mecanismo denominado sombreado: El parámetro `x` sombrea cualquier variable con el mismo nombre, pero solo dentro de la función que define el parámetro.

Esto significa que el código anterior producirá la siguiente salida:

```
Ingresa un número: 1
1234
```


