# LABORATORIO: Anagrama

Un anagrama es una nueva palabra formada al reorganizar las letras de una palabra, usando todas las letras originales exactamente una vez. Por ejemplo, las frases "rail safety" y "fairy tales" son anagramas, mientras que "I am" y "You are" no lo son.

Tu tarea es escribir un programa que:

* Le pida al usuario dos textos por separado.
* Compruebe si los textos ingresados son anagramas e imprima el resultado.

A tener en cuenta:

* Supongamos que dos cadenas vacías no son anagramas.
* Tratar a las letras mayúsculas y minúsculas como iguales.
* Los espacios no se toman en cuenta durante la verificación: trátalos como inexistentes.

Prueba tu código utilizando los datos que te proporcionamos.

## Datos de prueba

* Ejemplo 1
    * Entrada de muestra:
    ```
    Listen
    Silent 
    ```
    * Salida de muestra: 
    ```
    Anagramas
    ```
* Ejemplo 2
    * Entrada de muestra:
    ```
    modern
    norman 
    ```
    * Salida de muestra: 
    ```
    No son anagramas
    ```