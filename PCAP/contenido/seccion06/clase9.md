# LABORATORIO: ¡Encuentra una palabra!

Vamos a jugar un juego. Te daremos dos cadenas: una es una palabra (por ejemplo, "dog") y la segunda es una combinación de un grupo de caracteres.

Tu tarea es escribir un programa que responda la siguiente pregunta: ¿Los caracteres que comprenden la primera cadena están ocultos dentro de la segunda cadena?

Por ejemplo:

* Si la segunda cadena es "vcxzxduybfdsobywuefgas", la respuesta es si;
* Si la segunda cadena es "vcxzxdcybfdstbywuefsas", la respuesta es no (ya que no están las letras "d", "o", o "g" ni en ese orden)

Pistas:

* Debes usar las variantes de dos argumentos del método `find()` dentro de tu código.
* No te preocupes por mayúsculas y minúsculas.

Prueba tu código utilizando los datos que te proporcionamos.

## Datos de prueba

* Ejemplo 1
    * Entrada de muestra:
    ```
    donor
    Nabucodonosor 
    ```
    * Salida de muestra: 
    ```
    Sí
    ```
* Ejemplo 2
    * Entrada de muestra:
    ```
    donut
    Nabucodonosor 
    ```
    * Salida de muestra: 
    ```
    No
    ```