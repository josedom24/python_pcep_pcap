# Propiedades de clase

Las **variables de clase** son un concepto fundamental en la programación orientada a objetos en Python. A diferencia de las variables de instancia, que pertenecen a objetos específicos, las variables de clase son compartidas por todas las instancias de una clase y existen independientemente de si hay objetos creados o no. Vamos a profundizar en este tema.

## Definición y creación de variables de clase

Una variable de clase se define dentro de la clase pero fuera de cualquier método. Por ejemplo:

```
class ClaseEjemplo:
    contador = 0  # Variable de clase

    def __init__(self, val=1):
        self.__propiedad1 = val
        ClaseEjemplo.contador += 1  # Incrementa el contador en cada instancia creada
```

En este caso, `contador` se inicializa en 0 y se incrementa cada vez que se crea una nueva instancia de `ClaseEjemplo`.

Veamos cómo se comportan las variables de clase con el siguiente código:

```
objeto1 = ClaseEjemplo()
objeto2 = ClaseEjemplo(2)
objeto3 = ClaseEjemplo(4)

print(objeto1.__dict__, objeto1.contador)
print(objeto2.__dict__, objeto2.contador)
print(objeto3.__dict__, objeto3.contador)
```

Al ejecutar el código, la salida es la siguiente:

```
{'_ClaseEjemplo__propiedad1': 1} 3
{'_ClaseEjemplo__propiedad1': 2} 3
{'_ClaseEjemplo__propiedad1': 4} 3
```

* **Visibilidad de variables**: Las variables de clase, como `contador`, no aparecen en el diccionario `__dict__` de los objetos. Esto es natural, ya que estas variables no son propiedades del objeto en sí, sino de la clase. Sin embargo, aún puedes acceder a ellas a través del nombre de la clase, como `ClaseEjemplo.contador`.
* **Valor compartido**:  La variable de clase `contador` presenta el mismo valor en todas las instancias de la clase. En este caso, cada vez que se crea un nuevo objeto, `contador` se incrementa, reflejando el total de instancias creadas hasta el momento.


## Variables privadas de clases

```
class ClaseEjemplo:
    __contador = 0
    def __init__(self, val = 1):
        self.__propiedad1 = val
        ClaseEjemplo.__contador += 1


objeto1 = ClaseEjemplo()
objeto2 = ClaseEjemplo(2)
objeto3 = ClaseEjemplo(4)

print(objeto1.__dict__, objeto1._ClaseEjemplo__contador)
print(objeto2.__dict__, objeto2._ClaseEjemplo__contador)
print(objeto3.__dict__, objeto3._ClaseEjemplo__contador)
```

En este ejemplo hemos nombrado la variable de clase con dos guiones bajos (`__`) indicando que es privada. Esto significa que la variable `__contador` de la clase es renombrada internamente como `_ClaseEjemplo__contador`. Así, aunque no es accesible directamente como `__contador`, podemos acceder a ella a través de su nombre alterado: `_ClaseEjemplo__contador`.

Analizando el código:

* La variable de clase `__contador` es incrementada cada vez que se crea una nueva instancia de la clase `ClaseEjemplo`.
* En el constructor, el atributo `__propiedad1` es asignado a cada instancia con el valor proporcionado.
* Cada instancia (`objeto1`, `objeto2`, `objeto3`) tendrá su propio valor de `__propiedad1` almacenado en el diccionario (`__dict__`).
* El valor de `__contador` será incrementado con cada instancia creada, alcanzando un valor de `3` al final.

La salida esperada es:

```
{'_ClaseEjemplo__propiedad1': 1} 3
{'_ClaseEjemplo__propiedad1': 2} 3
{'_ClaseEjemplo__propiedad1': 4} 3
```

## Existencia de las variables de clase

En Python, las **variables de clase** existen incluso cuando no se ha creado ninguna instancia de la clase. Esto es crucial para entender la diferencia entre las variables de clase y las variables de instancia, que se asignan a objetos individuales.

Veamos un ejemplo:

```
class ClaseEjemplo:
    varia = 1  # Variable de clase

    def __init__(self, val):
        ClaseEjemplo.varia = val  # Modificación de la variable de clase

# Imprime el diccionario de atributos de la clase antes de crear una instancia
print(ClaseEjemplo.__dict__)

# Crea una instancia de la clase
objeto = ClaseEjemplo(2)

# Imprime el diccionario de atributos de la clase después de crear una instancia
print(ClaseEjemplo.__dict__)

# Imprime el diccionario de atributos del objeto
print(objeto.__dict__)
```

* La clase `ClaseEjemplo` tiene una variable de clase `varia` inicializada con el valor `1`.
* En el constructor (`__init__`), en lugar de asignar `self.varia = val` (lo que crearía una variable de instancia), se modifica la variable de clase utilizando `ClaseEjemplo.varia = val`. Esto afecta a la variable de clase compartida por todas las instancias.
* **Antes de crear una instancia**, cuando imprimimos `ClaseEjemplo.__dict__`, veremos algo como:
    ```
    {'varia': 1, '__module__': '__main__', '__init__': <function ClaseEjemplo.__init__>, ...}
    ```
  Aquí `varia` tiene su valor inicial `1`.

* **Después de crear una instancia**, se actualiza `ClaseEjemplo.varia` al valor pasado al constructor, en este caso `2`. Si volvemos a imprimir `ClaseEjemplo.__dict__`, veremos:
    ```
    {'varia': 2, '__module__': '__main__', '__init__': <function ClaseEjemplo.__init__>, ...}
    ```
* El diccionario `__dict__` de un objeto contiene solo sus atributos específicos de instancia. En este caso, como no hemos definido ninguna variable de instancia en `objeto`, su `__dict__` estará vacío:

  ```
  {}
  ```

Es importante notar la diferencia entre estos dos conceptos:
* **Variables de clase**: Son compartidas por todas las instancias de la clase y se almacenan en el diccionario de la clase.
* **Variables de instancia**: Son propias de cada objeto y se almacenan en el diccionario del objeto.

El código asigna el valor de `varia` directamente a la clase, lo que afecta a todas las instancias. Si hubiéramos usado `self.varia`, habríamos creado una nueva variable específica para cada instancia.

