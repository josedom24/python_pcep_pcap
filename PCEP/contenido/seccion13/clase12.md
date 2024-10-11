# Ámbito de variables y funciones

El **alcance de un nombre** (por ejemplo, el nombre de una variable) es la parte del código donde el nombre es reconocido correctamente. También lo podemos llamar **ámbito de la variable**.

Por ejemplo, el alcance del parámetro de una función es la función en sí. El parámetro es inaccesible fuera de la función.
Otro ejemplo, las variables declaradas dentro de una función, sólo existen en esa función, fuera son inexistentes. Después veremos que lo contrarío no se cumple.

Ejemplo:

```
def scope_test():
    x = 123


scope_test()
print(x)
```

El programa no correrá. El mensaje de error dirá: `NameError: name 'x' is not defined`.

* Dentro de la función hemos declarado la variable `x`.
* Fuera de la función no existe la variable `x`.

## Variables fuera de la función

Comencemos revisando si una variable creada fuera de una función es visible dentro de una función. Para ello veamos el siguiente ejemplo:

```
def my_function():
    print("¿Conozco a la variable?", var)


var = 1
my_function()
print(var)
```

El resultado de la prueba es positivo, el código da como salida:

```
¿Conozco a la variable? 1
1
```
La respuesta es: **una variable que existe fuera de una función tiene alcance dentro del cuerpo de la función**.

Esta regla se rompe si **declaramos una variable dentro de la función con el mismo nombre**:

```
def my_function():
    var = 2
    print("¿Conozco a la variable?", var)


var = 1
my_function()
print(var)
```

Ahora la salida es:

```
¿Conozco a la variable? 2
1
```

La variable `var` creada dentro de la función no es la misma que la que se definió fuera de ella, parece ser que hay **dos variables diferentes con el mismo nombre**. La variable de la función es una *sombra* de la variable fuera de la función.

Una variable que existe fuera de una función tiene un alcance dentro del cuerpo de la función, excluyendo a aquellas que tienen el mismo nombre.

También significa que el alcance de una variable existente fuera de una función solo se puede implementar dentro de una función cuando su valor es leído. El asignar un valor hace que la función cree su propia variable.

