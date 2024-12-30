# Propiedades de instancia

En programación orientada a objetos, las clases pueden tener diferentes tipos de datos que actúan como propiedades. En Python, estas propiedades pueden ser definidas y manipuladas a través de **variables de instancia**, que son características que pertenecen a objetos específicos, no a la clase en su conjunto.

Cuando se crea un objeto a partir de una clase, se pueden establecer propiedades que son únicas para cada instancia. Estas propiedades se pueden definir durante la inicialización del objeto mediante un constructor, pero también se pueden agregar o eliminar en cualquier momento de la vida del objeto. Esto ofrece flexibilidad, ya que diferentes instancias de la misma clase pueden tener diferentes conjuntos de propiedades.

Todas las variables de instancia de objeto se almacenan dentro de un diccionario dedicado llamado `__dict__`, contenido en cada objeto por separado.

Consideremos la siguiente clase de ejemplo:

```
class ClaseEjemplo:
    def __init__(self, val=1):
        self.propiedad1 = val

    def crear_nueva_propiedad(self, val):
        self.propiedad2 = val

objeto1 = ClaseEjemplo()
objeto2 = ClaseEjemplo(2)
objeto2.crear_nueva_propiedad(3)
objeto3 = ClaseEjemplo(4)
objeto3.propiedad3 = 5

print(objeto1.__dict__)
print(objeto2.__dict__)
print(objeto3.__dict__)
```

En este ejemplo, se crean tres objetos de `ClaseEjemplo`. Cada uno tiene propiedades distintas:

- `objeto1` solo contiene la propiedad `propiedad1`.
- `objeto2` incluye tanto `propiedad1` como `propiedad2`.
- `objeto3`, además de `propiedad1`, tiene una propiedad adicional `propiedad3`, que se le asigna después de su creación.

La salida del programa revela las propiedades de cada objeto:
```
{'propiedad1': 1}
{'propiedad1': 2, 'propiedad2': 3}
{'propiedad1': 4, 'propiedad3': 5}
```

Es fundamental destacar que las variables de instancia están aisladas entre sí. Modificar la propiedad de un objeto no afecta a los demás. Esto permite que cada objeto mantenga su propio estado sin interferencias externas.


## Encapsulación

En Python, la **encapsulación** es un principio clave de la programación orientada a objetos, y se puede lograr utilizando **variables de instancia privadas**. Esto se consigue anteponiendo dos guiones bajos (`__`) al nombre de una variable. Veamos cómo funciona esto y qué implicaciones tiene.

Cuando se define una variable de instancia con dos guiones bajos, como `__propiedad1`, Python transforma internamente su nombre para incluir el nombre de la clase. Esto significa que se convierte en `_ClaseEjemplo__propiedad1`. Este mecanismo, conocido como *name mangling*, hace que la variable sea menos accesible desde fuera de la clase.


Aquí hay un ejemplo que ilustra este comportamiento:

```
class ClaseEjemplo:
    def __init__(self, val=1):
        self.__propiedad1 = val

    def crear_nueva_propiedad(self, val=2):
        self.__propiedad2 = val

objeto1 = ClaseEjemplo()

objeto2 = ClaseEjemplo(2)
objeto2.crear_nueva_propiedad(3)

objeto3 = ClaseEjemplo(4)
objeto3.__propiedad3 = 5

print(objeto1.__dict__)
print(objeto2.__dict__)
print(objeto3.__dict__)
```

La salida de este código es la siguiente:
```
{'_ClaseEjemplo__propiedad1': 1}
{'_ClaseEjemplo__propiedad1': 2, '_ClaseEjemplo__propiedad2': 3}
{'_ClaseEjemplo__propiedad1': 4, '__propiedad3': 5}
```

Podemos observar que las variables `__propiedad1` y `__propiedad2` han sido transformadas, mientras que `__propiedad3`, que se añadió directamente al objeto fuera de la clase, no se ha modificado y se muestra como una propiedad pública.

## Acceso a variables privadas

Aunque se pueden considerar privadas, estas variables aún son accesibles desde fuera de la clase utilizando su nombre "mangled". Por ejemplo, puedes acceder a `__propiedad1` así:

```
print(objeto1._ClaseEjemplo__propiedad1)  # Salida: 1
```

Es importante notar que la privacidad en Python es más una convención que una regla estricta. Aunque las variables con dos guiones bajos son más difíciles de acceder, no son completamente inaccesibles. Además, si se intenta agregar una propiedad fuera de la clase, esta no se someterá al *name mangling* y se comportará como una propiedad normal.

