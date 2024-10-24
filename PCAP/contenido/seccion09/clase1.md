# Propiedades de instancia

En programación orientada a objetos, las clases pueden tener diferentes tipos de datos que actúan como propiedades. En Python, estas propiedades pueden ser definidas y manipuladas a través de variables de instancia, que son características que pertenecen a objetos específicos, no a la clase en su conjunto.

Cuando se crea un objeto a partir de una clase, se pueden establecer propiedades que son únicas para cada instancia. Estas propiedades se pueden definir durante la inicialización del objeto mediante un constructor, pero también se pueden agregar o eliminar en cualquier momento de la vida del objeto. Esto ofrece flexibilidad, ya que diferentes instancias de la misma clase pueden tener diferentes conjuntos de propiedades.

Todas las variables de instancia de objeto se almacenan dentro de un diccionario dedicado llamado `__dict__`, contenido en cada objeto por separado.

Consideremos la siguiente clase de ejemplo:

```
class ExampleClass:
    def __init__(self, val=1):
        self.first = val

    def set_second(self, val):
        self.second = val

example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)
example_object_2.set_second(3)
example_object_3 = ExampleClass(4)
example_object_3.third = 5

print(example_object_1.__dict__)
print(example_object_2.__dict__)
print(example_object_3.__dict__)
```

En este ejemplo, se crean tres objetos de `ExampleClass`. Cada uno tiene propiedades distintas:

- `example_object_1` solo contiene la propiedad `first`.
- `example_object_2` incluye tanto `first` como `second`.
- `example_object_3`, además de `first`, tiene una propiedad adicional `third`, que se le asigna después de su creación.

La salida del programa revela las propiedades de cada objeto:
```
{'first': 1}
{'first': 2, 'second': 3}
{'first': 4, 'third': 5}
```

Es fundamental destacar que las variables de instancia están aisladas entre sí. Modificar la propiedad de un objeto no afecta a los demás. Esto permite que cada objeto mantenga su propio estado sin interferencias externas.


## Encapsulación

En Python, la **encapsulación** es un principio clave de la programación orientada a objetos, y se puede lograr utilizando **variables de instancia privadas**. Esto se consigue anteponiendo dos guiones bajos (`__`) al nombre de una variable. Veamos cómo funciona esto y qué implicaciones tiene.

Cuando se define una variable de instancia con dos guiones bajos, como `__first`, Python transforma internamente su nombre para incluir el nombre de la clase. Esto significa que se convierte en `_ExampleClass__first`. Este mecanismo, conocido como *name mangling*, hace que la variable sea menos accesible desde fuera de la clase.


Aquí hay un ejemplo que ilustra este comportamiento:

```
class ExampleClass:
    def __init__(self, val=1):
        self.__first = val

    def set_second(self, val=2):
        self.__second = val

example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)

example_object_2.set_second(3)

example_object_3 = ExampleClass(4)
example_object_3.__third = 5

print(example_object_1.__dict__)
print(example_object_2.__dict__)
print(example_object_3.__dict__)
```

La salida de este código es la siguiente:
```
{'_ExampleClass__first': 1}
{'_ExampleClass__first': 2, '_ExampleClass__second': 3}
{'_ExampleClass__first': 4, '__third': 5}
```

Podemos observar que las variables `__first` y `__second` han sido transformadas, mientras que `__third`, que se añadió directamente al objeto fuera de la clase, no se ha modificado y se muestra como una propiedad pública.

## Acceso a variables privadas

Aunque se pueden considerar privadas, estas variables aún son accesibles desde fuera de la clase utilizando su nombre "mangled". Por ejemplo, puedes acceder a `__first` así:

```python
print(example_object_1._ExampleClass__first)  # Salida: 1
```

Es importante notar que la privacidad en Python es más una convención que una regla estricta. Aunque las variables con dos guiones bajos son más difíciles de acceder, no son completamente inaccesibles. Además, si se intenta agregar una propiedad fuera de la clase, esta no se someterá al *name mangling* y se comportará como una propiedad normal.

