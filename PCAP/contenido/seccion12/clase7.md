# Introducción a los cierres

Un **cierre** es una función que recuerda el entorno en el que se creó, incluso cuando esa función se invoca fuera de su contexto original. Esto significa que una función interna puede acceder a las variables de su función externa, incluso después de que la función externa ha terminado su ejecución.

Vamos a analizar el siguiente ejemplo:

```
def outer(par):
    loc = par

    def inner():
        return loc
    
    return inner

var = 1
fun = outer(var)
print(fun())
```

* Definimos las funciones:
   * `outer(par)`: Esta es una función que toma un argumento `par` y define una variable local `loc` igual a `par`.
   * `inner()`: Esta es una función interna definida dentro de `outer()`, que puede acceder a la variable `loc`.

2. La función externa devuelve la función interna:
   * `outer(var)` se invoca con `var = 1`. Esto significa que `loc` dentro de `outer()` se convierte en `1`.
   * `outer()` devuelve la función `inner()`, que se asigna a la variable `fun`.

3. Usamos el cierre: cuando se llama a `fun()`, se ejecuta `inner()`, que devuelve el valor de `loc`. A pesar de que `outer()` ya ha finalizado su ejecución, `inner()` todavía tiene acceso a `loc` debido a que es un cierre.

Los cierres son una poderosa herramienta para crear funciones más flexibles y mantener un estado entre llamadas a funciones sin tener que recurrir a variables globales.

## Cierres con parámetros

Los **cierres** permiten crear funciones internas que recuerdan el contexto de su función externa. Como mencionaste, se pueden diseñar cierres que tomen parámetros adicionales, lo que amplía su funcionalidad. Vamos a revisar el código que has proporcionado y su funcionamiento:

Veamos un ejemplo:

```
def make_closure(par):
    loc = par

    def power(p):
        return p ** loc
    return power

fsqr = make_closure(2)  # Cierre que eleva al cuadrado
fcub = make_closure(3)  # Cierre que eleva al cubo

for i in range(5):
    print(i, fsqr(i), fcub(i))
```

* Definimos la función `make_closure(par)`, que recibe un parámetro `par` y define una variable local `loc` que almacena ese valor.
   - Dentro de `make_closure`, se define una función interna llamada `power(p)`, que toma un argumento `p` y eleva `p` a la potencia de `loc`.
* Creamos los cierres
* Creamos los cierres:
   * `fsqr = make_closure(2)`: Esto crea un cierre que elevará cualquier número dado al cuadrado (2).
   * `fcub = make_closure(3)`: Esto crea otro cierre que elevará cualquier número dado al cubo (3).
* Usamos los cierres: en el bucle `for`, se itera desde 0 hasta 4. Para cada número `i`, se imprime el valor de `i`, el resultado de `fsqr(i)`, y el resultado de `fcub(i)`.

## Cuestionario

1. ¿Cuál es el resultado esperado del siguiente código?
    ```
    class Vowels:
        def __init__(self):
            self.vow = "aeiouy "  # Sí, sabemos que y no siempre se considera una vocal.
            self.pos = 0

        def __iter__(self):
            return self

        def __next__(self):
            if self.pos == len(self.vow):
                raise StopIteration
            self.pos += 1
            return self.vow[self.pos - 1]


    vowels = Vowels()
    for v in vowels:
        print(v, end=' ')
    ```

2. Escribe una función lambda, estableciendo a 1 su argumento entero, y aplícalo a la función map() para producir la cadena 1 3 3 5 en la consola.
    ```
    any_list = [1, 2, 3, 4]
    even_list = # Completar las líneas aquí.
    print(even_list)
    ```

3. ¿Cuál es el resultado esperado del siguiente código?
    ```
    def replace_spaces(replacement='*'):
        def new_replacement(text):
            return text.replace(' ', replacement)
        return new_replacement


    stars = replace_spaces()
    print(stars("And Now for Something Completely Different"))
    ```

## Solución cuestionario

1. Pregunta 1

    `a e i o u y`

2. Pregunta 2

    `list(map(lambda n: n | 1, any_list)`

3. Pregunta 3

    `And*Now*for*Something*Completely*Different`