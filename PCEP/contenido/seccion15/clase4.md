# Métodos de diccionarios

## El método keys()

Utilizando el método `keys()` de los diccionarios podemos recorrerlos utilizando un bucle `for`.
El método `keys()` nos devuelve una lista de todas las claves del diccionario. Al tener una lista de claves se puede acceder a todo el diccionario de una manera fácil y útil.

Veamos un ejemplo:

```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

for key in dictionary.keys():
    print(key, "->", dictionary[key])
```

Para ordenar la salida podemos usar la función `sorted()` de esta manera:

```
...
for key in sorted(dictionary.keys()):
```

## Los métodos item() y values()

Otra manera de hacer el recorrido es utilizar el método `items()`. Este método devuelve una lista de tuplas, donde cada tupla es un par de clave y valor.

Ejemplo:
```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

for spanish, english in dictionary.items():
    print(spanish, "->", english)
```

También existe un método denominado `values()`, funciona de manera muy similar al de `keys()`, pero regresa una lista de valores.

Ejemplo:
```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

for english in dictionary.values():
    print(english)
```
Hay que recordar que si tenemos el valor no podemos calcular la clave con la que es referenciada.

## Modificar, agregar y eliminar valores

El asignar un nuevo valor a una clave existente es sencillo, debido a que los diccionarios son completamente mutables, no existen obstáculos para modificarlos.

Se va a reemplazar el valor "cat" por "supercat":

Observa:
```
dictionary = {'gato': 'cat', 'perro': 'dog', 'caballo': 'horse'}

dictionary['gato'] = 'supercat'
print(dictionary)
```

## Agregando nuevas claves

El agregar una nueva clave con su valor a un diccionario es tan simple como cambiar un valor. Solo se tiene que asignar un valor a una nueva clave que no haya existido antes.

Ejemplo:

```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

dictionary['cisne'] = 'swan'
print(dictionary)
```

También es posible insertar un elemento al diccionario utilizando el método `update()`, por ejemplo:

```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

dictionary.update({"pato": "duck"})
print(dictionary)
```

## Eliminado una clave

Al eliminar la clave también se removerá el valor asociado. Los valores no pueden existir sin sus claves. Esto se logra con la instrucción `del`.

A continuación un ejemplo:
```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

del dictionary['perro']
print(dictionary)
```

Al eliminar una clave no existente, provocará un error.

Para eliminar el ultimo elemento de la lista, se puede emplear el método `popitem()`:
```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

dictionary.popitem()
print(dictionary)    # salida: {'gato': 'cat', 'perro': 'dog'}
```

En versiones anteriores de Python, por ejemplo, antes de la 3.6.7, el método popitem() elimina un elemento al azar del diccionario.

## Copiar diccionarios

Para copiar un diccionario, emplea el método `copy()`:
```
pol_esp_dictionary = {
    "zamek" : "castillo",
    "woda"  : "agua",
    "gleba" : "tierra"
    }

copy_dictionary = pol_esp_dictionary.copy()
```

## El método clear()

El método `clear()` elimina todos los pares de clave-valor de un diccionario:

```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}

dictionary.clear()
print(dictionary)
```
