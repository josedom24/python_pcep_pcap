# LABORATORIO: El dígito de la vida

Algunos dicen que el Dígito de la Vida es un dígito calculado usando el cumpleaños de alguien. Es simple: solo necesitas sumar todos los dígitos de la fecha. Si el resultado contiene más de un dígito, se debe repetir la suma hasta obtener exactamente un dígito. Por ejemplo:

* 1 Enero 2017 = 2017 01 01
* 2 + 0 + 1 + 7 + 0 + 1 + 0 + 1 = 12
* 1 + 2 = 3

3 es el dígito que buscamos y encontramos.

Tu tarea es escribir un programa que:

* Le pregunté al usuario su cumpleaños (en el formato AAAAMMDD o AAAADMM o MMDDAAAA; en realidad, el orden de los dígitos no importa).
* Dé como salida El Dígito de la Vida para la fecha ingresada.

Prueba tu código utilizando los datos que te proporcionamos.

## Datos de prueba

* Ejemplo 1
    * Entrada de muestra:
    ```
    19991229
    ```
    * Salida de muestra: 
    ```
    6
    ```
* Ejemplo 2
    * Entrada de muestra:
    ```
    20000101
    ```
    * Salida de muestra: 
    ```
    4
    ```