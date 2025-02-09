#  LABORATORIO: Mejorando el cifrado César

## Escenario

Ya estás familiarizado con el cifrado César, y es por eso que queremos que mejores el código que te mostramos recientemente.

El cifrado César original cambia cada carácter por otro: `a` se convierte en `b`, `z` se convierte en `a`, y así sucesivamente. Hagámoslo un poco más difícil y permitamos que el valor desplazado provenga del rango 1 - 25.

Además, dejemos que el código conserve las mayúsculas y minúsculas (las minúsculas permanecerán en minúsculas) y todos los caracteres no alfabéticos deben permanecer intactos.

Tu tarea es escribir un programa el cual:

* Le pida al usuario una línea de texto para encriptar.
* Le pida al usuario un valor de cambio (un número entero del rango 1..25, nota: debes validar la entrada para asegurarnos que l número está dentro del rango).
* Imprime el texto codificado. 

Prueba tu código utilizando los datos que te proporcionamos.

## Datos de prueba

* Ejemplo 1
    * Entrada de muestra:
    ```
    abcxyzABCxyz 123
    2 
    ```
    * Salida de muestra: 
    ```
    cdezabCDEzab 123
    ```
* Ejemplo 2
    * Entrada de muestra:
    ```
    The die is cast
    25 
    ```
    * Salida de muestra: 
    ```
    Sgd chd hr bzrs
    ```
