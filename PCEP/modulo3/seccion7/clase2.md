# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 6: Operaciones con listas
## Clase: Arreglos de dos dimensiones

### Listas dentro de listas

En muchas ocasiones los datos que queremos guardar en nuestro programa tienen la forma de una tabla, es decir, los datos estñ´an distribuido por filas y columnas.

Por ejemplo, si queremos representar en una variable un tablero de ajedrez para guardar las posiciones de las piezas, tendremos que buscar una estructura que nos permita guardar la información estructura en filas y columnas. Un tablero de ajedrez tiene ocho filas y ochos columnas

Para guardar está información en Python utilizaremos listas. Como hemos estudiado una lista puede guardar elementos de cualquier tipo de datos, por lo tanto si tengo una lista cuyo elementos son listas estaría guardando los datos en una tabla. Por ejemplo para guardar el tablero de ajedrez tendríamos una lista con 8 elementos, y cada uno de estos elementos serían listas, que representan las filas. Cada lista que representa las filas tendría 8 elementos que representan las columnas.

A esta estructura la podemos nombrar como **arays o arreglos bidimensiones, o tablas o matriz**.

### Declaración de arreglos bidimensionales

Como vimos anteriormente para las listas tenemos varios formas de inicializar un arreglo bidimensional. Para realizar estos ejemplos vamos a crear una tabla de 3 filas y tres columnas con los 9 primeros números. Veamos las distintas alternativas:

1. En la declaración de la variable, por ejemplo:

    ```
    tabla = [[1, 2, 3],[4, 5, 6],[7, 8, 9]]
    ```

2. Usando compresión de listas:

    ```
    tabla = [ ]
    tabla.append([i for i in range(1,4)])
    tabla.append([i for i in range(4,7)])
    tabla.append([i for i in range(7,10)])
    ```

    Como vemos vamos añadiendo a una lista vacía distintos elementos que son listas que hemos creado con compresión de listas. El problema es que si tiene muchos filas, tenemos que incluir muchas instrucciones con el método `append()`. Para solucionarlo podemos realizar una compresión de lista más compleja donde la expresión es una compresión de lista:

    ```
    tabla = [[fila * 3 + columna + 1 for columna in range(3)] for fila in range(3)]
    ```
### Indexación de arreglos bidimensionales

Para acceder a un elemento de un arreglo bidimensional tendremos que indicar la fila y la columna en la que se encuentra. Por supuesto la primera fila y la primera columna estarán en la posición. De esta manera:

```
print(tabla[0][0]) # Imprime el elemento que está en la primera fila y primera columna.
print(tabla[1][2]) # Imprime el elemento que está en la segunda fila y tercera columna.
print(tabla[2][2]) # Imprime el elemento que está en la tercera fila y tercera columna.
```

Evidentemente también podemos cambiar el valor de un determinado elemento:

```
tabla[2][0] = 0 # Modificamos el elemento guardado en la tercera fila y primera columna.
```

### Recorrido de arreglos bidimensionales

Para recorres todos los elementos de un arreglo bidimensional, necesitamos posicionarnos en cada una de las filas y posteriormente en cada una de las columnas para indexar el elemento que queremos mostrar, operar o modificar. 

Para realizar este recorrido necesitamos dos bucles anidados, el primero nos permite recorrer las filas y el segundo cada elemento de esa fila. Si queremos imprimir la tabla que hemos declarado:

```
tabla = [[1, 2, 3],[4, 5, 6],[7, 8, 9]]
for fila in tabla:
    for elemento in fila:
         print(elemento," ",end="")
    print()
```
Fíjate que hemos ejecutado una instrucción `print()` que añade un salto de línea cada vez que terminamos de imprimir una fila.

También podríamos usar índices para recorrer una lista. De esta forma podríamos inicializar los valores de un arreglo bidimensioonal de forma interactiva. Vemos el ejemplo:

```
tabla = []
num_filas=3
num_columnas=3
for f in range(num_filas):
    new_fila = []
    for c in range(num_columnas):
        print("Introduce el elemento que estará en la psoición ",f,"-",c,":")
        elemento = int(input())
        new_fila.append(elemento)
    tabla.append(new_fila)
print(tabla)
```

* Creamos dos variables: `num_filas` y `num_columnas` para guardar el número de filas y números de columnas. Nos servirán para recorrer la tabla.
* Además cada vez que empezamos añadir una nueva fila, inicalizamos la variable temporal `new_fila` donde guardaremos los elementos de una fila.
* Cuando se termina de rellenar los elementos de una fila, esa lista se añade al arreglo y se vuelve a inicializar a lista vacía.

## Ejemplo tablero de ajedrez

Vamos a crear una arreglo bidimensional que representa un tablero de ajedrez. Cada elemento será una cadena que indica la pieza que está colocada o si está libre. Veamos el ejemplo:

```
EMPTY = "-"
PAWN = "PEON"
ROOK = "TORRE"
KNIGHT = "CABALLO"
board = []

for i in range(8):
    row = [EMPTY for i in range(8)]
    board.append(row)

board[0][0] = ROOK
board[0][7] = ROOK
board[7][0] = ROOK
board[7][7] = ROOK
board[4][2] = KNIGHT
board[3][4] = PAWN

print(board)

for fila in board:
    for elemento in fila:
         print(elemento," ",end="")
    print()
```

### Ejemplo estación meteorológica

Imagina que desarrollas un programa para una estación meteorológica automática. El dispositivo registra la temperatura del aire cada hora y lo hace durante todo el mes. Esto te da un total de 24 × 31 = 744 valores. Intentemos diseñar una lista capaz de almacenar todos estos resultados. 

1. Decidimos que para guardar la temperatura vamos a usar un número flotante.
2. Vamos a usar un arreglo bidimensional para guardar la información.
3. Decidimos que en cada fila guardaremos las temperaturas de cada hora, es decir tendrá 24 elementos.
4. El arreglo tendrá 31 filas, ya que cada fila se asignará a un día del mes, es decir el areglo tendrá una dimensión de 24 x 31.

Si queremos crear el arreglo y lo inicializamos a 0, sería de la siguiente manera:

```
temperaturas = [[0.0 for h in range(24)] for d in range(31)]
```

Vamos suponer que la matriz se actualiza automáticamente utilizando agentes de hardware especiales. Nosotros vamos a simular ese comportamiento actualizando la matriz con temperaturas aleatorias.

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)
print(temperaturas)
```