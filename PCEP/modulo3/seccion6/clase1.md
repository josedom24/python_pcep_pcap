# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 6: Operaciones con listas
## Clase: Las listas son mutables

## Las listas son mutables

Como hemos indicado en clases anteriores el tipo de datos lista es una **clase**, cada vez que creamos una variable de la clase lista estamos creando un **objeto** que además de guardar un conjunto de datos, posee un conjunto de **métodos** que nos permiten trabajar con la lista.

## ¿Qué significa que las listas son mutables?

Los elementos de las listas se pueden modificar:

```
lista1 = [1,2,3]
lista1[2]=4
print(lista1) #	[1, 2, 4]
del lista1[2]
print(lista1) # [1, 2]
```

Esto también ocurre cuando usamos los métodos, es decir, los métodos de las listas modifican el contenido de la lista, por ejemplo si usamos el método `append()` para añadir un elemento a la lista:

```
lista1.append(3)
print(lista1) # [1, 2, 3]
```

Como vemos la lista `lista1` se ha modificado.

## ¿Cómo se copian las listas?

Para copiar una lista en otra no podemos utilizar el operador de asignación:

```
lista1 = [1,2,3]
lista2 = lista1
lista1[1] = 10
print(lista2) # [1, 10, 3]
```

El operador de asignación no crea una nueva lista, sino que nombra con dos nombres distintos a la misma lista. No se guardan dos listas distintas en memoria, sino que la lista esta guardada en memoria pero se puede referenciar con dos nombres.

En la siguiente clase veremos la solución a cómo poder copiar listas de manera adecuada.

