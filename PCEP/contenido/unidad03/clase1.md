# Literales y tipos de datos

## Literales

Los literales nos permiten representar valores.

* Por ejemplo, `123`. Representa el número *ciento veintitrés*.
* Otro ejemplo, `c`. ¿Representa algún valor? Tal vez. Puede ser el símbolo de la velocidad de la luz, por ejemplo. También puede representar la constante de integración. Incluso la longitud de una hipotenusa en el Teorema de Pitágoras. Existen muchas posibilidades. No se puede elegir el valor correcto sin algo de conocimiento adicional.
* `123` es un literal, y `c` no lo es.

Se utilizan literales para codificar datos y ponerlos dentro del código. 

Veamos el siguiente ejemplo:

```
print("2")
print(2)
```

La segunda instrucción parece ser errónea debido a la falta visible de comillas. Intenta ejecutarlo. Si todo salió bien, ahora deberías de ver dos líneas idénticas. 

Nos encontramos con dos tipos diferentes de literales:

* Una **cadena**, la cual ya conoces.
* Y un **número entero**.

La función `print()` los muestra exactamente de la misma manera. Sin embargo, internamente, aunque en la memoria del ordenador sólo se pueden guardar datos binarios (formados por 0 y 1), el carácter "2" de la cadena se guardara con su código binario correspondiente, el número entero 2, se guardará de forma binaria.

En resumen, los valores que podemos representar con literales pueden ser de diferentes tipos:

* **Literales numéricos**: Que nos permiten representar números enteros y fraccionarios (reales). 
    * Los ordenadores guardan y operan con los números utilizando el sistema binario. Internamente todos los números se representan, se guardan y se operan utilizando 0 y 1.
    * Son de dos tipos:
        * **Enteros**, es decir, aquellos que no tienen una parte fraccionaria.
        * Y números **punto-flotantes** (o simplemente **flotantes** o **reales**), los cuales contienen (o son capaces de contener) una parte fraccionaría.
        * La característica del valor numérico que determina el tipo, rango y aplicación se denomina el **tipo**.
        * Si se codifica un literal y se coloca dentro del código de Python, la forma del literal determina la representación (tipo) que Python utilizará para almacenarlo en la memoria.
        * Por ejemplo:
            * `3`: es un literal numérico de tipo entero.
            * `3.0`: es un literal numérico de tipo flotante.
    * Ambos tipos difieren significativamente en como son almacenados internamente en el ordenador y en el rango de valores que aceptan.
* **Literales cadenas**: Nos permiten representar cadenas de caracteres. Para delimitar las cadenas podemos usar el carácter ' o el carácter ". 

