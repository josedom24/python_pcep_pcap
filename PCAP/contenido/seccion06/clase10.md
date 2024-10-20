# LABORATORIO: Sudoku

Como probablemente sabes, Sudoku es un rompecabezas de colocación de números jugado en un tablero de 9x9. El jugador tiene que llenar el tablero de una manera muy específica:

* Cada fila del tablero debe contener todos los dígitos del 0 al 9 (el orden no importa).
* Cada columna del tablero debe contener todos los dígitos del 0 al 9 (nuevamente, el orden no importa).
* Cada uno de los 9 subcuadros de 3x3 de la tabla debe contener todos los dígitos del 0 al 9.

Si necesitas más detalles, puedes encontrarlos [aquí](https://en.wikipedia.org/wiki/Sudoku).

Tu tarea es escribir un programa que:

* Lea las 9 filas del Sudoku, cada una con 9 dígitos (verifica cuidadosamente si los datos ingresados son válidos).
* Da como salida `Si` si el Sudoku es válido y `No` de lo contrario.

Prueba tu código utilizando los datos que te proporcionamos.

## Datos de prueba

* Ejemplo 1
    * Entrada de muestra:
    ```
    295743861
    431865927
    876192543
    387459216
    612387495
    549216738
    763524189
    928671354
    154938672 
    ```
    * Salida de muestra: 
    ```
    Sí
    ```
* Ejemplo 2
    * Entrada de muestra:
    ```
    195743862
    431865927
    876192543
    387459216
    612387495
    549216738
    763524189
    928671354
    254938671 
    ```
    * Salida de muestra: 
    ```
    No
    ```