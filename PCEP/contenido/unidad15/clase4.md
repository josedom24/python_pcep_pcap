# Métodos de diccionarios

## El método keys()

Utilizando el método `keys()` de los diccionarios podemos recorrerlo utilizando un bucle `for`.
El método `keys()` nos devuelve una lista de todas las claves dentro del diccionario. Al tener una lista de claves se puede acceder a todo el diccionario de una manera fácil y útil.

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

Otra manera de hacer el recorrido es utilizar el método `items()`. Este método devuelve una lista de tuplas, donde cada tupla es un par de cada clave con su valor.

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

Hay que recordar que si tenemos el valor no podemos calcular la calve con la que es referenciada.
