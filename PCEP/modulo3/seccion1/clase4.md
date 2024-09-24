# Ejemplos de estructuras condicionales

## Analizando ejemplos de código

Ahora te mostraremos algunos programas simples pero completos. No los explicaremos a detalle, porque consideramos que los comentarios (y los nombres de las variables) dentro del código son guías suficientes.

Todos los programas resuelven el mismo problema: encuentran el número mayor de una serie de números y lo imprimen.

## Ejemplo 1:

Comenzaremos con el caso más simple: ¿Cómo identificar el mayor de los dos números?

```
#Se leen dos números
number1 = int(input("Ingresa el primer número: "))
number2 = int(input("Ingresa el segundo número: "))

# Elige el número más grande
if number1 > number2:
    larger_number = number1
else:
    larger_number = number2

# Imprime el resultado
print("El número más grande es:", larger_number)
```

El fragmento de código anterior debe estar claro: lee dos valores enteros, los compara y encuentra cuál es el más grande.

## Ejemplo 2:

Ahora vamos a mostrarte un hecho intrigante. Python tiene una característica interesante, mira el código a continuación:

```
#Se leen dos números
number1 = int(input("Ingresa el primer número: "))
number2 = int(input("Ingresa el segundo número: "))

# Elige el número más grande
if number1 > number2: larger_number = number1
else: larger_number = number2

# Imprime el resultado
print("El número más grande es:", larger_number)
```

Nota: si alguna de las ramas de if-elif-else contiene una sola instrucción, puedes codificarla de forma más completa (no es necesario que aparezca una línea con sangría después de la palabra clave), pero solo continúa la línea después de los dos puntos).

Sin embargo, este estilo puede ser engañoso, y no lo vamos a usar en nuestros programas futuros, pero definitivamente vale la pena saber si quieres leer y entender los programas de otra persona.

No hay otras diferencias en el código.

## Ejemplo 3:

Es hora de complicar el código: encontremos el mayor de los tres números. ¿Se ampliará el código? Un poco.

Suponemos que el primer valor es el más grande. Luego verificamos esta hipótesis con los dos valores restantes.

Observa el siguiente código:

```
# Se leen tres números
number1 = int(input("Ingresa el primer número: "))
number2 = int(input("Ingresa el segundo número: "))
number3 = int(input("Ingresa el tercer número: "))

# Asumimos temporalmente que el primer número
# es el más grande.
# Lo verificaremos pronto.
largest_number = number1

# Comprobamos si el segundo número es más grande que el mayor número actual
# y actualiza el número más grande si es necesario.
if number2 > largest_number:
    largest_number = number2

# Comprobamos si el tercer número es más grande que el mayor número actual
# y actualiza el número más grande si es necesario.
if number3 > largest_number:
    largest_number = number3

# Imprime el resultado.
print("El número más grande es:", largest_number)
```

Este método es significativamente más simple que tratar de encontrar el número más grande comparando todos los pares de números posibles (es decir, el primero con el segundo, el segundo con el tercero y el tercero con el primero). Intenta reconstruir el código por ti mismo.

## Pseudocódigo e introducción a los bucles (ciclos)

Ahora deberías poder escribir un programa que encuentre el mayor de cuatro, cinco, seis o incluso diez números. Ya conoces el esquema, por lo que ampliar el tamaño del problema no será particularmente complejo.

¿Pero qué sucede si te pedimos que escribas un programa que encuentre el mayor de doscientos números? ¿Te imaginas el código? Necesitarás doscientas variables. Si doscientas variables no son lo suficientemente complicadas, intenta imaginar la búsqueda del número más grande de un millón.

Imagina un código que contiene 199 sentencias condicionales y doscientas invocaciones de la función `input()`. Por suerte, no necesitas lidiar con eso. Hay un enfoque más simple.

Vamos a intentar diseñar un **algoritmo** sin usar la sintaxis de Python. Intentaremos analizar el problema y determinar los pasos tenemos que dar (algoritmo) usando una notación, que no es un lenguaje de programación real (no se puede compilar ni ejecutar), pero está formalizado, es conciso y se puede leer. Se llama **pseudocódigo**.


Veamos nuestro pseudocódigo a continuación:

```
1 largest_number = -999999999
2 Leer(number)
3 if number == -1:
     Escribir(largest_number)
     Terminar
4 if number > largest_number:
     largest_number = number
5 Ir a la línea 2
```

* En primer lugar, podemos simplificar el programa si, al principio del código, le asignamos a la variable `largest_number` un valor que será más pequeño que cualquiera de los números ingresados. Usaremos -999999999 para ese propósito.
* En segundo lugar, asumimos que nuestro algoritmo no sabrá por adelantado cuántos números se entregarán al programa. Esperamos que el usuario ingrese todos los números que desee; el algoritmo funcionará bien con cien y con mil números. ¿Cómo hacemos eso?
* Hacemos un trato con el usuario: cuando se ingresa el valor `-1`, será una señal de que no hay más datos y que el programa debe finalizar su trabajo.
* De lo contrario, si el valor ingresado no es igual a `-1`, el programa leerá otro número, y así sucesivamente.

El truco se basa en la suposición de que cualquier parte del código se puede realizar más de una vez, precisamente, tantas veces como sea necesario. La ejecución de una determinada parte del código más de una vez se denomina **bucle**. El significado de este término es probablemente obvio para ti.

Cuando se llega a la línea 5 se vuelve a ejecutar desde la la línea 2, se realiza un bucle. Los pasaremos tantas veces como sea necesario para revisar todos los valores ingresados.

¿Puedes usar una estructura similar en un programa escrito en Python? Si, si puedes, lo estudiaremos más adelante.

## Información Adicional

Python a menudo viene con muchas funciones integradas que harán el trabajo por ti. Por ejemplo, para encontrar el número más grande de todos, puede usar una función incorporada de Python llamada `max()`. Puedes usarlo con múltiples argumentos. Analiza el código de abajo:

```
# Se leen tres números.
number1 = int(input("Ingresa el primer número: "))
number2 = int(input("Ingresa el segundo número: "))
number3 = int(input("Ingresa el tercer número: "))

# Verifica cuál de los números es el mayor
# y pásalo a la variable largest_number
    
largest_number = max(number1, number2, number3)

# Imprime el resultado.
print("El número más grande es:", largest_number)
```

De la misma manera, puedes usar la función `min()` para devolver el número más pequeño. 