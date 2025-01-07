# Introducción a los cierres

Un **cierre** es una función que recuerda el entorno en el que se creó, incluso cuando esa función se invoca fuera de su contexto original. Esto significa que una función interna puede acceder a las variables de su función externa, incluso después de que la función externa ha terminado su ejecución.

Vamos a analizar el siguiente ejemplo:

```
def externa(par):
    loc = par

    def interna():
        return loc
    
    return interna

var = 1
fun = externa(var)
print(fun())
```

* Definimos las funciones:
   * `externa(par)`: Esta es una función que toma un argumento `par` y define una variable local `loc` igual a `par`.
   * `interna()`: Esta es una función interna definida dentro de `externa()`, que puede acceder a la variable `loc`.
* La función externa devuelve la función interna:
   * `externa(var)` se invoca con `var = 1`. Esto significa que `loc` dentro de `externa()` se convierte en `1`.
   * `externa()` devuelve la función `interna()`, que se asigna a la variable `fun`.
* Usamos el cierre: cuando se llama a `fun()`, se ejecuta `interna()`, que devuelve el valor de `loc`. A pesar de que `externa()` ya ha finalizado su ejecución, `interna()` todavía tiene acceso a `loc` debido a que es un cierre.

Los cierres son una poderosa herramienta para crear funciones más flexibles y mantener un estado entre llamadas a funciones sin tener que recurrir a variables globales.

## Cierres con parámetros

Los **cierres** permiten crear funciones internas que recuerdan el contexto de su función externa. Como mencionaste, se pueden diseñar cierres que tomen parámetros adicionales, lo que amplía su funcionalidad. Veamos un ejemplo:


```
def cierre(par):
    loc = par

    def potencia(p):
        return p ** loc
    return potencia

fsqr = cierre(2)  # Cierre que eleva al cuadrado
fcub = cierre(3)  # Cierre que eleva al cubo

for i in range(5):
    print(i, fsqr(i), fcub(i))
```

* Definimos la función `cierre(par)`, que recibe un parámetro `par` y define una variable local `loc` que almacena ese valor.
   - Dentro de `cierre`, se define una función interna llamada `potencia(p)`, que toma un argumento `p` y eleva `p` a la potencia de `loc`.
* Creamos los cierres
* Creamos los cierres:
   * `fsqr = cierre(2)`: Esto crea un cierre que elevará cualquier número dado al cuadrado (2).
   * `fcub = cierre(3)`: Esto crea otro cierre que elevará cualquier número dado al cubo (3).
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