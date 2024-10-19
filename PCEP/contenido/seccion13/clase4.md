# Paso de parámetros

Podemos pasar los parámetros a una función de dos maneras:

## Paso de parámetro posicionales

La técnica que asigna cada argumento al parámetro correspondiente según su posición, es llamada **paso de parámetros posicionales**, los argumentos pasados de esta manera son llamados **argumentos posicionales**.

Ejemplo:

```
def my_function(a, b, c):
    print(a, b, c)

my_function(1, 2, 3)
```

Veamos otro ejemplo, vamos a crear una función que nos permita presentarnos, tendremos que enviar nuestro nombre y nuestro apellido:

```
def presentacion(nombre, apellido):
    print("Hola, mi nombre es", nombre, apellido)

presentacion("Luke", "Skywalker")
presentacion("Jesse", "Quick")
presentacion("Clark", "Kent")
```

El primer argumento se copiará en el parámetro `nombre` y el segundo en el parámetro `apellidos`.

## Paso de parámetros con palabra clave

Python ofrece otra manera de pasar argumentos, donde **el significado del argumento está definido por su nombre**, no su posición, a esto se le denomina paso de **parámetros con palabra clave**. Los argumentos pasados de esta manera son llamados **argumentos por palabra**.

Observa el siguiente código:

```
def presentacion(nombre, apellido):
    print("Hola, mi nombre es", nombre, apellido)

presentacion(nombre = "James", apellido = "Bond")
presentacion(apellido = "Skywalker", nombre = "Luke")
```

El concepto es claro: los valores pasados a los parámetros son precedidos por el nombre del parámetro al que se le va a pasar el valor, seguido por el signo de =.

La posición no es relevante aquí, cada argumento conoce su destino porque indicamos el nombre del parámetro.


Por supuesto que no se debe de utilizar el nombre de un parámetro que no existe.

El siguiente código provocará un error de ejecución:

```
presentacion(apellidos="Skywalker", nombre="Luke")
```

Esto es lo que Python arrojará: `TypeError: presentacion() got an unexpected keyword argument 'apellidos'`

## Combinar argumentos posicionales y de palabra clave

Es posible combinar ambos tipos si se desea, solo tenemos que tener en cuenta que **se deben colocar primero los argumentos posicionales y después los de palabra clave**.

Veamos un ejemplo, vamos a calcular e imprimir la suma de todos sus argumentos.

```
def sumar(a, b, c):
    print(a, "+", b, "+", c, "=", a + b + c)

sumar(1, 2, 3)
```

Dará como salida: `1 + 2 + 3 = 6`.

Hemos usado el paso de argumentos por posicional, pero también podemos usar el paso de argumentos por palabra clave:

```
sumar(c = 1, a = 2, b = 3)
```

El programa dará como salida lo siguiente: `2 + 3 + 1 = 6`

Ahora intentemos mezclar ambas formas.

```
sumar(3, c = 1, b = 2)
```

Vamos a analizarla:

* El argumento `3` para el parámetro `a` es pasado utilizando la forma posicional.
* Los argumentos para `c` y `b` son especificados con palabras clave.

Esto es lo que se verá en la consola: `3 + 2 + 1 = 6`

Veamos otra llamada a la función:

```
sumar(3, a = 1, b = 2)
```

La respuesta de Python es: `TypeError: sumar() got multiple values for argument 'a'`.

## Parámetros predefinidos

Es posible que en ocasiones el valor de ciertos argumentos son más utilizados que otros. En este caso podemos indicar un valor predefinido que tendrá el parámetro cuando el argumento correspondiente ha sido omitido.

Si consideramos que un apellido muy común es `Rodríguez`, podemos indicar este valor como valor predefinido del parámetro `apellido`:

```
def presentacion(nombre, apellido="Rodríguez"):
    print("Hola, mi nombre es", nombre, apellido)
```

Solo se tiene que colocar el nombre del parámetro seguido del signo de = y el valor por defecto.

Ahora podemos llamar a la función indicando los dos argumentos:
```
presentacion("Jorge", "Pérez")
```

Pero también podemos usar la función indicando sólo el argumento correspondiente al `nombre`. Podemos hacerlo de dos maneras distintas:

```
presentacion("Enrique")
presentacion(nombre="Enrique")
```

Con ambas instrucciones la salida será `Hola, mi nombre es Enrique González`.

Hay que indicar que **después de un parámetro con un valor predefinido, no podemos poner un parámetro sin valor predefinido, es decir la siguiente declaración daría un error:

```
def presentacion(nombre="Jose", apellido):
    print("Hola, mi nombre es", nombre, apellido)
```

El error sería: `SyntaxError: non-default argument follows default argument`.

Para terminar, indicar que podemos usar valores predefinidos para cualquiera de los parámetros.

```
def presentacion(nombre="Juan", apellido="González"):
    print("Hola, mi nombre es", nombre, apellido)
```

Esto hace que la siguiente invocación sea completamente valida: 

```
presentacion()
```
Y esta es la salida esperada: `Hola, mi nombre es Juan González`.

Si solo se especifica un argumento de palabra clave, el restante tomará el valor por defecto:

```
presentacion(last_name="Rodríguez")
```

La salida es: `Hola, mi nombre es Juan Rodríguez`.


## Cuestionario

1. ¿Cuál es la salida del siguiente código?

```
def intro(a="James Bond", b="Bond"):
    print("Mi nombre es", b + ".", a + ".")

intro()
```
2. ¿Cuál es la salida del siguiente código?
```
def intro(a="James Bond", b="Bond"):
    print("Mi nombre es", b + ".", a + ".")

intro(b="Sergio López")
```
3. ¿Cuál es la salida del siguiente fragmento de código?
```
def intro(a, b="Bond"):
    print("Mi nombre es", b + ".", a + ".")

intro("Susan")
```
4. ¿Cuál es la salida del siguiente código?
```
def add_numbers(a, b=2, c):
    print(a + b + c)

add_numbers(a=1, c=3)
```

## Solución cuestionario

1. Pregunta 1

`Mi nombre es Bond. James Bond.`

2. Pregunta 2

`Mi nombre es Sergio López. James Bond`

3. Pregunta 3

`Mi nombre es Bond. Susan.`

4. Pregunta 4

`SyntaxError - a non-default argument (c) follows a default argument (b=2)`


