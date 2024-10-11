# Conversión de datos (casting)

Python ofrece dos funciones para convertir a un tipo de dato y resolver este problema, aquí están: `int()` y `float()`.

Sus nombres indican cual es su función:

* La función `int()` toma un argumento (por ejemplo, una cadena: *int(string)*) e intenta convertirlo a un valor entero; si llegase a fallar, el programa entero fallará también (existe una manera de solucionar esto, se explicará mas adelante).
* La función `float()` toma un argumento (por ejemplo, una cadena: *float(string)*) e intenta convertirlo a flotante.

Estas funciones se pueden utilizar directamente pasando el resultado de la función `input()` directamente. No hay necesidad de emplear variables como almacenamiento intermedio.

Veamos un ejemplo:

```
anything = float(input("Inserta un número: "))
something = anything ** 2.0
print(anything, "al cuadrado es", something)
```

* En este caso el valor leído por la función `input()` (una cadena), se convierte a un valor numérico flotante con la función `float()`
* En la variable `something` se guarda un número y es de tipo `float`. 
* Ahora se puede hacer la operación matemática sin problemas. 
* Y finalmente se muestra el resultado con la función `print()`.

## Posibilidades que nos ofrece la conversión de tipos

Trabajar con la funciones `input()`, `int()` y `float()` se nos abre muchas nuevas posibilidades. 

Podremos escribir programas que lean de la consola, tanto cadenas de texto como números, que podremos procesar y operar.

En este momento, los programas que podemos escribir serán muy básicos ya que no podrán tomar decisiones, y consecuentemente no son capaces de reaccionar acorde a cada situación.

Veamos otros ejemplo. El siguiente ejemplo hace referencia al programa anterior que calcula la longitud de la hipotenusa. Vamos a reescribirlo, para que pueda leer las longitudes de los catetos desde la consola:

```
leg_a = float(input("Inserta la longitud del primer cateto: "))
leg_b = float(input("Inserta la longitud del segundo cateto: "))
hypo = (leg_a**2 + leg_b**2) ** .5
print("La longitud de la hipotenusa es:", hypo)
```

* El programa pide que el usuario introduzca dos números flotantes, correspondientes a la longitud de los catetos.
* Y calcula la hipotenusa e imprime el resultado.

Veamos a una segunda versión de este programa. Observa, que la variable `hypo` se usa con un solo propósito: guardar el valor calculado para posteriormente imprimirlo en pantalla.

Debido a que la función `print()` acepta el paso de varios argumentos, se puede **quitar la variable del código**:

```
leg_a = float(input("Inserta la longitud del primer cateto: "))
leg_b = float(input("Inserta la longitud del segundo cateto: "))
print("La longitud de la hipotenusa es: ", (leg_a**2 + leg_b**2) ** .5)
```
