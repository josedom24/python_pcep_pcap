# Repaso de listas por compresión

Las **listas por comprensión** son una característica poderosa y elegante en Python que te permite crear listas de manera concisa en una sola línea, eliminando la necesidad de usar bucles explícitos o funciones adicionales como `append()`. A continuación te muestro un ejemplo y las reglas que rigen su creación y uso.

En el primer ejemplo, usamos un bucle `for` tradicional para generar una lista de potencias de 10:

```
list_1 = []

for ex in range(6):
    list_1.append(10 ** ex)

print(list_1)
```

La misma lista se puede generar con una **lista por comprensión** de manera mucho más compacta:

```
list_2 = [10 ** ex for ex in range(6)]
print(list_2)
```

Una **lista por comprensión** es una construcción que permite generar una nueva lista aplicando una expresión a cada elemento de una secuencia o iterable. 
La sintaxis básica es:

```
[nueva_expresión for elemento in iterable]
```

Se puede desglosar en tres partes:

1. **`nueva_expresión`**: La operación que se realiza en cada elemento del iterable, en este caso `10 ** ex` (potencia de 10).
2. **`for elemento in iterable`**: La parte del bucle que recorre el iterable (`range(6)` en este ejemplo).

## Añadiendo condiciones a una lista por comprensión

La **expresión condicional** en Python es una herramienta versátil y poderosa que se puede utilizar para hacer selecciones entre dos valores basándose en una condición. Aunque puede parecer inusual a primera vista, es una manera muy concisa de expresar una lógica condicional simple, similar a la estructura `if-else`, pero en una sola línea.

La sintaxis de una expresión condicional es la siguiente:

```
expresión_uno if condición else expresión_dos
```

Podemos añadir una expresión condicional dentro de una **lista por comprensión**, lo que hace el código más conciso:

```
the_list = [1 if x % 2 == 0 else 0 for x in range(10)]
print(the_list)
```

## Generadores y listas por compresión

Las **listas por comprensión** y los **generadores** comparten una sintaxis similar, pero tienen diferencias clave en cómo funcionan y en su uso de memoria. Mientras que las listas por comprensión crean la lista en su totalidad de una vez, los generadores producen los elementos uno por uno, lo que permite un uso más eficiente de la memoria cuando trabajamos con grandes cantidades de datos.

A continuación, un ejemplo que muestra las dos variantes:

```
the_list = [1 if x % 2 == 0 else 0 for x in range(10)]  # Lista por comprensión
the_generator = (1 if x % 2 == 0 else 0 for x in range(10))  # Generador
```

* **Listas por comprensión**: Se utilizan corchetes `[ ]`. Esto crea y almacena toda la lista en memoria inmediatamente.
* **Generadores**: Se utilizan paréntesis `( )`. En lugar de crear toda la lista, se producen valores uno por uno según se necesiten.

Ambos producirán la misma salida cuando se itere sobre ellos:

```
for v in the_list:
    print(v, end=" ")
print()

for v in the_generator:
    print(v, end=" ")
print()
```


Aunque la salida parece idéntica, el comportamiento detrás de escena es diferente. En el caso de la lista, todos los valores ya están calculados y almacenados en memoria. En cambio, el generador calcula cada valor solo cuando es necesario, sin mantener todos los elementos en memoria a la vez.

Una forma sencilla de verificar que el segundo es un generador es intentar obtener su longitud usando `len()`:

```
len(the_list)  # Devuelve 10
len(the_generator)  # Genera TypeError
```

La función `len()` falla con un generador porque los generadores no tienen todos sus elementos disponibles en memoria. El error será:

```
TypeError: object of type 'generator' has no len()
```

## Uso con un bucle

No necesitas almacenar ni la lista ni el generador si solo quieres utilizarlos una vez en un bucle:

```
# Usando lista por comprensión
for v in [1 if x % 2 == 0 else 0 for x in range(10)]:
    print(v, end=" ")
print()

# Usando generador
for v in (1 if x % 2 == 0 else 0 for x in range(10)):
    print(v, end=" ")
print()
```

Ambos bucles producirán el mismo resultado. Sin embargo, en el primer caso, toda la lista se crea antes de comenzar el bucle. En el segundo caso, los valores se generan uno por uno, lo que ahorra memoria.

