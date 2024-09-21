# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 5: Ordenando listas simples: el ordenamiento de burbuja
##  Clase: Resumen y cuestionario de la sección

### Resumen de sección

1. HHemos estudiado el **algoritmo de ordenación de listas burbuja** y hemos visto la necesidad de usar **anidación de bucles** para ordenar una lista usando este algoritmo.
2. Puedes usar el método sort() para ordenar los elementos de una lista, por ejemplo:
```
lst = [5, 3, 1, 2, 4]
print(lst)

lst.sort()
print(lst)  # outputs: [1, 2, 3, 4, 5]
```

3. También hay un método de lista llamado reverse(), que puedes usar para invertir la lista, por ejemplo:
```
lst = [5, 3, 1, 2, 4]
print(lst)

lst.reverse()
print(lst)  # salida: [4, 2, 1, 3, 5]
```

### Cuestionario de sección

1. ¿Cuál es la salida del siguiente fragmento de código?

```
lst = ["D", "F", "A", "Z"]
lst.sort()

print(lst)
```

2. ¿Cuál es la salida del siguiente fragmento de código?

```
a = 3
b = 1
c = 2

lst = [a, c, b]
lst.sort()

print(lst)
```

3. ¿Cuál es la salida del siguiente fragmento de código?

```
a = "A"
b = "B"
c = "C"
d = " "

lst = [a, b, c, d]
lst.reverse()

print(lst)
```

### Solución cuestionario

1. Pregunta 1:

```
['A', 'D', 'F', 'Z']
```

2. Pregunta 2:

```
[1, 2, 3]
```

3. Pregunta 3:

```
[' ', 'C', 'B', 'A']
```

