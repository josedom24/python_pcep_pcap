# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 2: Literales de Python 
## Clase: Literales y tipos de datos

## Literales, los datos en si mismos

Un literal se refiere a datos cuyos valores están determinados por el literal mismo. Los literales nos permiten representar valores.

Por ejemplo, `123`. ¿Puedes adivinar qué valor representa? Claro que puedes: es *ciento veintitrés*.
Otro ejemplo, `c`. ¿Representa algún valor? Tal vez. Puede ser el símbolo de la velocidad de la luz, por ejemplo. También puede representar la constante de integración. Incluso la longitud de una hipotenusa en el Teorema de Pitágoras. Existen muchas posibilidades. No se puede elegir el valor correcto sin algo de conocimiento adicional.

Y esta es la pista: `123` es un literal, y `c` no lo es.

Se utilizan literales para codificar datos y ponerlos dentro del código. 

Veamos el siguiente ejemplo:

```
print("2")
print(2)
```

La segunda instrucción parece ser errónea debido a la falta visible de comillas. Intenta ejecutarlo. Si todo salió bien, ahora deberías de ver dos líneas idénticas. ¿Qué paso? ¿Qué significa?

Nos encontramos con dos tipos diferentes de literales:

* Una **cadena**, la cual ya conoces.
* Y un **número entero**.

La función `print()` los muestra exactamente de la misma manera. Sin embargo, internamente, aunque en la memoria del ordenador sólo se pueden guardar datos binarios (formados por 0 y 1), el carácter "2" de la cadena se guardara con su código binario correspondiente, el número entero 2, se guardará de forma binaria.

En resumen, los valores que podemos representar con literales pueden ser de diferentes tipos:

* **Literales numéricos**: Que nos permiten representar números enteros y fraccionarios (reales).
* **Literales cadenas**: Nos permiten representar cadenas de caracteres. Para delimitar las cadenas podemos usar el carácter ' o el carácter ". 