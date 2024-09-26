# Introducción a las funciones

Vamos a escribir nuestro primer programa muy sencillo.

Para ello puede usar el IDLE: crea un nuevo archivo fuente de Python, coloca este código, nombra el archivo y guárdalo. Ahora ejecútalo. Si todo sale bien, verás el texto contenido entre comillas en la ventana de la consola IDLE. 

El código que tienes que escribir es:

```
print("¡Hola, Mundo!")
```

Este programa esta compuesto por una instrucción con los siguientes elementos:

* La palabra `print`.
* Un paréntesis de apertura.
* Una comilla.
* Una línea de texto: `¡Hola, Mundo!`.
* Otra comilla.
* Un paréntesis de cierre.

## La función print()

La palabra `print` es un nombre de una **función**. 

Las funciones de Python son similares a las funciones matemáticas, sin embargo, son más flexibles y pueden tener más características que las funciones matemática.

Una función en python es un código fuente independiente de nuestro programa, el cual es capaz de:

* **Causar algún efecto** (por ejemplo, enviar texto a la terminal, crear un archivo, dibujar una imagen, reproducir un sonido, etc.).
* **Evaluar o devolver un valor**, es decir recibir datos, hacer cálculos con ellos y devolver un resultado (por ejemplo, la raíz cuadrada de un valor o la longitud de un texto dado).

Además, muchas de las funciones de Python pueden hacer las dos cosas anteriores juntas.

¿Dónde pueden estar definidas las funciones?

* **Pueden estar definidas en Python por defecto**. La función `print` es una de este tipo. Esta función está integrada con Python. Son conocidas también como funciones predefinidas, y la podemos usar cuando queramos. Python 3.7.1 viene con 69 funciones incorporadas. Puedes encontrar su lista completa en orden alfabético en [Python Standard Library](https://docs.python.org/3.7/library/functions.html).
* **Pueden provenir de uno o varios de los módulos de Python** llamados complementos o librerías; algunos de los módulos vienen con Python, otros pueden requerir una instalación por separado. Para utilizar estas funciones hay que indicar la librería donde se encuentran.
* **Puedes escribirlas tú mismo**, colocando tantas funciones como desees y necesites dentro de tu programa para hacerlo más simple, claro y elegante.

El nombre de la función debe ser significativo (el nombre de la función `print` es evidente), imprime en la terminal.

Si vas a utilizar alguna función ya existente, no podrás modificar su nombre, pero cuando comiences a escribir tus propias funciones, debes considerar cuidadosamente la elección de nombres.

## Argumentos de funciones

Al utilizar una función (a esto lo llamamos **llamar o invocar a una función**) podemos indicarle algún dato que llamamos **argumentos o parámetros**. Estos serán necesarios para causar algún efecto o devolver alguna información.

Una función puede recibir varios argumentos, según los datos que necesite para realizar su tarea. En ocasiones, es posible, que la función no reciba ningún argumento.

Los argumentos se deben indicar dentro de los **paréntesis de la función**. Si vas a utilizar una función que no tiene ningún argumento, aún tiene que tener los paréntesis.

En nuestro programa de ejemplo estamos trabajando con la función `print()`. Y cómo vemos tiene un argumento.

## Una cadena como el argumento de la función print()

El único argumento entregado a la función `print()` en este ejemplo es una **cadena de caracteres**: `"Hola, Mundo!"`.

Como puedes ver, **la cadena está delimitada por comillas**, de hecho, las comillas forman la cadena, recortan una parte del código y le asignan un significado diferente. Podemos imaginar que las comillas significan algo así: el texto entre nosotros no es un código. No está diseñado para ser ejecutado, y se debe tomar tal como está.

## Invocación de funciones

El nombre de la función (`print` en este caso) junto con los paréntesis y los argumento(s), forman la **invocación de la función**.

```
print("¡Hola, Mundo!") 
```

¿Qué sucede cuando Python encuentra una invocación de una función?

1. Python comprueba si el nombre especificado es **legal** (explora sus datos internos para encontrar una función existente del nombre; si esta búsqueda falla, Python aborta el código).
2. Python comprueba si los requisitos de la función para el número de argumentos **le permiten invocar** la función de esta manera (por ejemplo, si una función específica exige exactamente dos argumentos, cualquier invocación que entregue solo un argumento se considerará errónea y abortará la ejecución del código).
3. **Python deja el código por un momento** y salta dentro de la función que se desea invocar; por lo tanto, también toma los argumentos y los pasa a la función.
4. La función **ejecuta el código**, provoca el efecto deseado (si lo hubiera), evalúa el (los) resultado(s) deseado(s) y termina la tarea.
5. Python regresa al código (al lugar inmediatamente después de la invocación) y reanuda su ejecución.
