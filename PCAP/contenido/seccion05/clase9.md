# Ordenación de cadenas

La **ordenación** en Python está estrechamente relacionado con la comparación, ya que ordenar es esencialmente un proceso que involucra comparaciones repetidas entre elementos. En el caso de listas que contienen cadenas, la ordenación es una operación común, como cuando se trabaja con listas de nombres, productos o ciudades.

Python ofrece dos maneras principales de ordenar listas: usando la función `sorted()` o el método `sort()`.

## Uso de la función `sorted()`

La función `sorted()` toma una lista como argumento y devuelve una **nueva lista** con los elementos ordenados, mientras que la lista original permanece sin cambios. Esto es útil cuando deseas mantener la lista original intacta pero necesitas una versión ordenada de la misma.

Ejemplo:

```
greek = ['omega', 'alpha', 'pi', 'gamma']
greek_sorted = sorted(greek)

print(greek)        # Lista original intacta
print(greek_sorted) # Lista ordenada
```

En este caso, la lista `greek` no cambia, pero `greek_sorted` es una nueva lista con los elementos ordenados alfabéticamente.

## Uso del método `sort()`

El método `sort()` ordena la lista **en su lugar**, es decir, modifica directamente la lista original sin crear una nueva. Este método es útil cuando no necesitas mantener la versión original de la lista.

Ejemplo:

```
greek = ['omega', 'alpha', 'pi', 'gamma']

print(greek)  # Lista original
greek.sort()
print(greek)  # Lista ordenada en su lugar
```

En este caso, la lista original `greek` se ha modificado, y ahora está ordenada alfabéticamente.

Si deseas un ordenamiento diferente al predeterminado (por ejemplo, en orden inverso o con criterios especiales), puedes modificar el comportamiento de ambas funciones utilizando parámetros adicionales, lo cual será tratado más adelante.

