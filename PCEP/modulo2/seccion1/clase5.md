# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 1: El Programa "¡Hola, Mundo!"
## Clase: Más sobre argumentos en funciones

## Usando múltiples argumentos

Hasta ahora hemos probado el comportamiento de la función `print()` sin argumentos y con un argumento. También vale la pena intentar alimentar a la función `print()` con más de un argumento.

Escribe el siguiente programa:

```
print("La Araña Witsi Witsi" , "subió" , "a su telaraña.")
```

Hay una invocación de la función `print()`, pero contiene tres argumentos. Todos ellos son cadenas.

Los argumentos están **separados por comas**. Los hemos rodeado de espacios para hacerlos más visibles, pero no es realmente necesario, y no lo haremos más. Los distintos argumentos que mandamos a una función hay que separarlos por comas.

Si observas el código nuevamente, verás que hay no hay espacios dentro de las cadenas.

Al ejecutar el código aparecerá el siguiente texto:

```
La Araña Witsi Witsi subió a su telaraña.
```

Los espacios, eliminados de las cadenas, han vuelto a aparecer. ¿Puedes explicar por qué?

Dos conclusiones emergen de este ejemplo:

* La función `print()` invocada con más de un argumento los muestra todos en una sola línea.
* La función `print()` pone un espacio entre los argumentos de salida por iniciativa propia.

## Argumentos posicionales

Escribe el siguiente programa:

```
print("Mi nombre es", "Python.")
print("Monty Python.")
```

La forma en que estamos pasando los argumentos a la función `print()` es la más común en Python, y se llama la **forma posicional**. Este nombre proviene del hecho de que el significado del argumento está dictado por su posición (por ejemplo, el segundo argumento se mostrará después del primero, no al revés).

Ejecuta el código y comprueba si el resultado coincide con tus predicciones.

## Argumentos de palabra clave

Python ofrece otro mecanismo para el paso de argumentos: **argumentos de palabras clave**. El nombre proviene del hecho de que el significado de estos argumentos se toma no de su ubicación (posición) sino de la palabra especial (palabra clave) utilizada para identificarlos.

La función `print()` tiene dos argumentos de palabra clave que puedes usar para tus propósitos. El primero se llama `end`. Para ver cómo funciona escribe este código:

```
print("Mi nombre es", "Python.", end=" ")
print("Monty Python.")
```

Para usarlo, es necesario conocer algunas reglas:

* **Un argumento de palabra clave consta de tres elementos**: una palabra clave se identifica el argumento (`end` aquí); un signo de igual (=); y un valor asignado a ese argumento;
* Cualquier argumento de palabra clave **debe colocarse después del último argumento posicional** (esto es muy importante).

En nuestro ejemplo, hemos utilizado el argumento de palabra clave `end`, y lo hemos configurado como cadena que contiene un espacio. Al ejecutar el programa se muestra el siguiente texto:

```
Mi nombre es Python. Monty Python.
```

Como puedes ver, el argumento de palabra clave `end` determina los caracteres que la función `print()` envía a la salida una vez que llega al final de sus argumentos posicionales. El comportamiento predeterminado refleja la situación en la que el argumento de palabra clave `end` se usa implícitamente de la siguiente manera: `end="\n"`.


¿Qué ocurre si asignamos al argumento de palabra clave `end` una cadena vacía?: Como el argumento `end` se ha establecido a nada, la función print() tampoco genera nada, una vez que se han agotado sus argumentos posicionales. Compruébalo ejecutando el siguiente código:

```
print("Mi nombre es ", end="")
print("Monty Python.")
```

Dijimos anteriormente que la función `print()` separa sus argumentos de salida con espacios. Este comportamiento también se puede cambiar. El argumento de palabra clave que puede hacer esto se denomina `sep` (como en separador).

Veamos el siguiente código:

```
print("Mi", "nombre", "es", "Monty", "Python.", sep="-")
```

La ejecución producirá el siguiente texto:

```
Mi-nombre-es-Monty-Python.
```

La función `print()` ahora usa un guión, en lugar de un espacio, para separar los argumentos de salida. Nota: el valor del argumento `sep` también puede ser una cadena vacía. Pruébalo tu mismo.

Ambos argumentos de palabra clave **pueden mezclarse en una invocación**, Veamos un ejemplo:

```
print("Mi", "nombre", "es", sep="_", end="*")
print("Monty", "Python.", sep="*", end="*\n")
```

El ejemplo no tiene mucho sentido, pero presenta de forma visible las interacciones entre `end` y `sep`. ¿Puedes predecir el resultado?

Ejecuta el código y comprueba si coincide con tus predicciones.
