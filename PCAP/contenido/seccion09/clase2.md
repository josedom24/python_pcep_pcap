# Propiedades de clase

Las **variables de clase** son un concepto fundamental en la programación orientada a objetos en Python. A diferencia de las variables de instancia, que pertenecen a objetos específicos, las variables de clase son compartidas por todas las instancias de una clase y existen independientemente de si hay objetos creados o no. Vamos a profundizar en este tema.

## Definición y creación de variables de clase

Una variable de clase se define dentro de la clase pero fuera de cualquier método. Por ejemplo:

```
class ExampleClass:
    counter = 0  # Variable de clase

    def __init__(self, val=1):
        self.__first = val
        ExampleClass.counter += 1  # Incrementa el contador en cada instancia creada
```

En este caso, `counter` se inicializa en 0 y se incrementa cada vez que se crea una nueva instancia de `ExampleClass`.

Veamos cómo se comportan las variables de clase con el siguiente código:

```
example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)
example_object_3 = ExampleClass(4)

print(example_object_1.__dict__, example_object_1.counter)
print(example_object_2.__dict__, example_object_2.counter)
print(example_object_3.__dict__, example_object_3.counter)
```

Al ejecutar el código, la salida es la siguiente:

```
{'_ExampleClass__first': 1} 3
{'_ExampleClass__first': 2} 3
{'_ExampleClass__first': 4} 3
```

* **Visibilidad de variables**: Las variables de clase, como `counter`, no aparecen en el diccionario `__dict__` de los objetos. Esto es natural, ya que estas variables no son propiedades del objeto en sí, sino de la clase. Sin embargo, aún puedes acceder a ellas a través del nombre de la clase, como `ExampleClass.counter`.
* **Valor compartido**:  La variable de clase `counter` presenta el mismo valor en todas las instancias de la clase. En este caso, cada vez que se crea un nuevo objeto, `counter` se incrementa, reflejando el total de instancias creadas hasta el momento.


## Variables de clases privadas

```
class ExampleClass:
    __counter = 0
    def __init__(self, val = 1):
        self.__first = val
        ExampleClass.__counter += 1


example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)
example_object_3 = ExampleClass(4)

print(example_object_1.__dict__, example_object_1._ExampleClass__counter)
print(example_object_2.__dict__, example_object_2._ExampleClass__counter)
print(example_object_3.__dict__, example_object_3._ExampleClass__counter)
```

En este ejemplo hemos nombrado la variable de clase con dos guiones bajos (`__`) indicando que es privada. Esto significa que la variable `__counter` de la clase es renombrada internamente como `_ExampleClass__counter`. Así, aunque no es accesible directamente como `__counter`, podemos acceder a ella a través de su nombre alterado: `_ExampleClass__counter`.

Analizando el código:

* La variable de clase `__counter` es incrementada cada vez que se crea una nueva instancia de la clase `ExampleClass`.
* En el constructor, el atributo `__first` es asignado a cada instancia con el valor proporcionado.
* Cada instancia (`example_object_1`, `example_object_2`, `example_object_3`) tendrá su propio valor de `__first` almacenado en el diccionario (`__dict__`).
* El valor de `__counter` será incrementado con cada instancia creada, alcanzando un valor de `3` al final.

La salida esperada es:

```python
{'_ExampleClass__first': 1} 3
{'_ExampleClass__first': 2} 3
{'_ExampleClass__first': 4} 3
```

## Existencia de las variables de clase

En Python, las **variables de clase** existen incluso cuando no se ha creado ninguna instancia de la clase. Esto es crucial para entender la diferencia entre las variables de clase y las variables de instancia, que se asignan a objetos individuales.

Veamos un ejemplo:






```python
class ExampleClass:
    varia = 1  # Variable de clase

    def __init__(self, val):
        ExampleClass.varia = val  # Modificación de la variable de clase

# Imprime el diccionario de atributos de la clase antes de crear una instancia
print(ExampleClass.__dict__)

# Crea una instancia de la clase
example_object = ExampleClass(2)

# Imprime el diccionario de atributos de la clase después de crear una instancia
print(ExampleClass.__dict__)

# Imprime el diccionario de atributos del objeto
print(example_object.__dict__)
```

### Explicación del Código

#### 1. Definición de la Clase y Variable de Clase
- La clase `ExampleClass` tiene una variable de clase `varia` inicializada con el valor `1`.
- En el constructor (`__init__`), en lugar de asignar `self.varia = val` (lo que crearía una variable de instancia), se modifica la variable de clase utilizando `ExampleClass.varia = val`. Esto afecta a la variable de clase compartida por todas las instancias.

#### 2. El Diccionario Interno de la Clase (`__dict__`)
El atributo especial `__dict__` en Python contiene todos los atributos de una clase u objeto, incluidos métodos, variables y otros componentes internos. 

- **Antes de crear una instancia**, cuando imprimimos `ExampleClass.__dict__`, veremos algo como:
  ```python
  {'varia': 1, '__module__': '__main__', '__init__': <function ExampleClass.__init__>, ...}
  ```
  Aquí `varia` tiene su valor inicial `1`.

- **Después de crear una instancia**, se actualiza `ExampleClass.varia` al valor pasado al constructor, en este caso `2`. Si volvemos a imprimir `ExampleClass.__dict__`, veremos:
  ```python
  {'varia': 2, '__module__': '__main__', '__init__': <function ExampleClass.__init__>, ...}
  ```

#### 3. El Diccionario del Objeto (`__dict__`)
El diccionario `__dict__` de un objeto contiene solo sus atributos específicos de instancia. En este caso, como no hemos definido ninguna variable de instancia en `example_object`, su `__dict__` estará vacío:

```python
{}
```

### Clave para Recordar

Es importante notar la diferencia entre estos dos conceptos:
- **Variables de clase**: Son compartidas por todas las instancias de la clase y se almacenan en el diccionario de la clase.
- **Variables de instancia**: Son propias de cada objeto y se almacenan en el diccionario del objeto.

El código asigna el valor de `varia` directamente a la clase, lo que afecta a todas las instancias. Si hubiéramos usado `self.varia`, habríamos creado una nueva variable específica para cada instancia.

### Conclusión

Este ejemplo demuestra cómo las variables de clase pueden existir y ser manipuladas incluso sin instanciar objetos, y cómo la estructura de los diccionarios `__dict__` refleja los cambios. Modificar las variables de clase a través de la clase afecta a todas las instancias, mientras que las variables de instancia son independientes para cada objeto.