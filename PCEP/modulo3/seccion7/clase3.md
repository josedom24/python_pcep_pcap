# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 6: Operaciones con listas
## Clase: Ejemplo con arreglo de doos dimensiones

### Ejemplo estación meteorológica

Imagina que desarrollas un programa para una estación meteorológica automática. El dispositivo registra la temperatura del aire cada hora y lo hace durante todo el mes. Esto te da un total de 24 × 31 = 744 valores. Intentemos diseñar una lista capaz de almacenar todos estos resultados. 

1. Decidimos que para guardar la temperatura vamos a usar un número flotante.
2. Vamos a usar un arreglo bidimensional para guardar la información.
3. Decidimos que en cada fila guardaremos las temperaturas de cada hora, es decir tendrá 24 elementos.
4. El arreglo tendrá 31 filas, ya que cada fila se asignará a un día del mes, es decir el areglo tendrá una dimensión de 24 x 31.

Si queremos crear el arreglo y lo inicializamos a 0, sería de la siguiente manera:

```
temperaturas = [[0.0 for h in range(24)] for d in range(31)]
```

Vamos suponer que la matriz se actualiza automáticamente utilizando agentes de hardware especiales. Nosotros vamos a simular ese comportamiento actualizando la matriz con temperaturas aleatorias.

```
import random

num_filas = 31
num_columnas = 24
temperaturas = [[0.0 for h in range(24)] for d in range(31)]

for dia in range(num_filas):
    for hora in range(num_columnas):
        temperaturas[dia][hora] = round(random.uniform(0, 40), 1)
print(temperaturas)
```