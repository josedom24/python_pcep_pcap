# Ejemplo con listas de dos dimensiones

## Ejemplo estación meteorológica

Imagina que desarrollas un programa para una estación meteorológica automática. El dispositivo registra la temperatura del aire cada hora y lo hace durante todo el mes. Esto te da un total de 24 × 31 = 744 valores. Intentemos diseñar una lista capaz de almacenar todos estos resultados. 

1. Decidimos que para guardar la temperatura vamos a usar un número flotante.
2. Vamos a usar una lista bidimensional para guardar la información.
3. Decidimos que en cada fila guardaremos las temperaturas de cada hora, es decir tendrá 24 elementos.
4. La lista tendrá 31 filas, ya que cada fila se asignará a un día del mes, es decir la lista tendrá una dimensión de 24 x 31.

Si queremos crear la lista e inicializarla a 0, sería de la siguiente manera:

```
temperaturas = [[0.0 for h in range(24)] for d in range(31)]
```

Vamos suponer que la matriz se actualiza automáticamente utilizando agentes de hardware especiales. Nosotros vamos a simular ese comportamiento actualizando la matriz con temperaturas aleatorias (no es muy real pero nos vale!!!).

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

# Actualizamos las temperaturas, con valores aleatorios.

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)
print(temperaturas)
```

## Ejercicio 1: Calcular la temperatura media mensual del mediodía

Creamos un programa para determinar la temperatura promedio mensual del mediodía. Suma las 31 lecturas registradas al mediodía y divida la suma por 31. 

El programa sería el siguiente:

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

# Actualizamos las temperaturas, con valores aleatorios.

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)

# Calculamos la temperatura media del mes al mediodía

total = 0.0

for temp_en_dia in temperaturas:
    total += temp_en_dia[11]

media = total / 31

print("Temperatura promedio al mediodía:", media)
```

* La variable `temp_en_dia` utilizada por el bucle `for` no es un escalar: cada paso a través de la matriz `temperaturas` lo asigna a la siguiente fila de la matriz.
* La temperatura al mediodía está guardada en la posición 11 de la fila (`temp_en_dia`) donde se guardan las temperaturas de cada hora.
* La variable `total` es una cumulador que nos permitirá ir sumando las temperaturas.

## Ejercicio 2: Calcular la temperatura más alta del mes

Vamos a escribir un programa que calcule la temperatura más alta. Veamos el código:

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

# Actualizamos las temperaturas, con valores aleatorios.

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)

# Calculamos la temperatura más alta
temp_mas_alta = -100.0

for temp_en_dia in temperaturas:
    for temp in temp_en_dia:
        if temp > temp_mas_alta:
            temp_mas_alta = temp

print("La temperatura más alta fue:", temp_mas_alta)
```

* La variable `temp_en_dia` itera en todas las filas de la matriz `temperaturas`.
* La variable `temp` itera a través de todas las mediciones tomadas en un día.
* La variable `temp_mas_alta` nos permite guardar las temperaturas que vamos recorriendo más altas. Lo inicializamos a un número muy pequeño.

## Ejercicio 3: Calcular los días en que las temperatura al mediodía fue menor que 20 ºC

Vamos a realizar un programa que calcule la cantidad de días en que las temperatura al mediodía fue menor que 20 ºC. Veamos el código:

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

# Actualizamos las temperaturas, con valores aleatorios.

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)

# Calculamos la cantidad de días en que las temperatura al mediodía fue menor que 20 ºC.


dias_calurosos = 0

temp_mas_alta = -100.0

for temp_en_dia in temperaturas:
    if temp_en_dia[11]>20:
        dias_calurosos += 1
        
print(dias_calurosos, "fueron los días calurosos.")
```

* En este programa usamos la variable `dias_calurosos` como contador para que nos cuente la cantidad de días que cumplen la condición.

## Introducción a las listas multidimensionales

¿Cómo cambiaría nuestra estructura donde guardamos las temperaturas, si quisiéramos guardar las temperaturas de cada mes del año?

En ese caso, necesitaríamos una lista de 3 dimensiones: una para guardar las temperaturas cada hora, otra para guardar los días y otra para guardar los meses.

Gráficamente sería un cubo (3 dimensiones) donde la lista bidimensional que hemos utilizado se repetiría 12 veces.

¿Y si además, quisiéramos guardar la información de cada año?

En el próximo apartado estudiaremos las listas multidimensionales.