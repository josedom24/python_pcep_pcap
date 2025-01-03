# Listas de dos dimensiones

## Listas dentro de listas

En muchas ocasiones los datos que queremos guardar en nuestro programa tienen la forma de una tabla, es decir, los datos están distribuidos por filas y columnas.

Por ejemplo, si queremos representar en una variable un tablero de ajedrez para guardar las posiciones de las piezas, tendremos que buscar una estructura que nos permita guardar la información estructurada en filas y columnas. Un tablero de ajedrez tiene ocho filas y ochos columnas

Para guardar está información en Python utilizaremos listas. Como hemos estudiado una lista puede guardar elementos de cualquier tipo de datos, por lo tanto si tengo una lista cuyo elementos son listas estaría guardando los datos en una tabla. Por ejemplo para guardar el tablero de ajedrez tendríamos una lista con 8 elementos, y cada uno de estos elementos serían listas, que representan las filas. Cada lista que representa las filas tendría 8 elementos que representan las columnas.

A esta estructura la podemos nombrar como **arays, arreglos bidimensiones, tablas o matrices**.

## Declaración de listas bidimensionales

Como vimos anteriormente para las listas tenemos varios formas de inicializar una lista bidimensional. Para realizar estos ejemplos vamos a crear una tabla de 3 filas y 3 columnas con los 9 primeros números. Veamos las distintas alternativas:

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

    Como vemos vamos añadiendo a una lista vacía distintos elementos que son listas que hemos creado con compresión de listas. El problema es que si tiene muchas filas, tenemos que incluir muchas instrucciones con el método `append()`. Para solucionarlo podemos realizar una compresión de lista más compleja donde la expresión es una compresión de lista:

    ```
    tabla = [[fila * 3 + columna + 1 for columna in range(3)] for fila in range(3)]
    ```
## Indexación de listas bidimensionales

Para acceder a un elemento de una lista bidimensional tendremos que indicar la fila y la columna (es decir, indicar en que lista nos posicionamos, y dentro de esa lista en que elemento) en la que se encuentra. Por supuesto la primera fila y la primera columna estarán en la posición 0,0. De esta manera:

```
print(tabla[0][0]) # Imprime el elemento que está en la primera fila y primera columna.
print(tabla[1][2]) # Imprime el elemento que está en la segunda fila y tercera columna.
print(tabla[2][2]) # Imprime el elemento que está en la tercera fila y tercera columna.
```

Evidentemente también podemos cambiar el valor de un determinado elemento:

```
tabla[2][0] = 0 # Modificamos el elemento guardado en la tercera fila y primera columna.
```

## Recorrido de listas bidimensionales

Para recorrer todos los elementos de una lista bidimensional, necesitamos posicionarnos en cada una de las filas y posteriormente en cada una de las columnas (es decir, ir recorriendo cada una de las listas que forman la lista y recorrerla) para indexar el elemento que queremos mostrar, operar o modificar. 

Para realizar este recorrido necesitamos dos bucles anidados, el primero nos permite recorrer las filas y el segundo cada elemento de esa fila. Si queremos imprimir la tabla que hemos declarado:

```
tabla = [[1, 2, 3],[4, 5, 6],[7, 8, 9]]
for fila in tabla:
    for elemento in fila:
         print(elemento," ",end="")
    print()
```
Fíjate que hemos ejecutado una instrucción `print()` que añade un salto de línea cada vez que terminamos de imprimir una fila.

También podríamos usar índices para recorrer una lista. De esta forma podríamos inicializar los valores de una lista bidimensional de forma interactiva. Vemos el ejemplo:

```
tabla = []
num_filas=3
num_columnas=3
for f in range(num_filas):
    new_fila = []
    for c in range(num_columnas):
        print("Introduce el elemento que estará en la posición ",f,"-",c,":")
        elemento = int(input())
        new_fila.append(elemento)
    tabla.append(new_fila)
print(tabla)
```

* Creamos dos variables: `num_filas` y `num_columnas` para guardar el número de filas y número de columnas. Nos servirán para recorrer la tabla.
* Además cada vez que empezamos a añadir una nueva fila, inicializamos la variable temporal `new_fila` donde guardaremos los elementos de una fila.
* Cuando se termina de rellenar los elementos de una fila, esa lista se añade a la lista principal y se vuelve a inicializar a lista vacía.

## Ejemplo tablero de ajedrez

Vamos a crear una lista bidimensional que representa un tablero de ajedrez. Cada elemento será una cadena que indica la pieza que está colocada o si está libre. Veamos el ejemplo:

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

