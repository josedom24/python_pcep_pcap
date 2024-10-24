# Relación entre superclase y subclase

En Python, la herencia es una característica fundamental de la programación orientada a objetos que permite establecer jerarquías entre clases. Una de las herramientas útiles para trabajar con estas relaciones de herencia es la función `issubclass()`. Esta función permite verificar si una clase es una subclase de otra, facilitando la comprensión y gestión de las relaciones entre clases.

## La función `issubclass()`

La función `issubclass()` tiene la siguiente sintaxis:

```
issubclass(ClassOne, ClassTwo)
```
* `ClassOne`: La clase que se está evaluando.
* `ClassTwo`: La clase que se considera como posible superclase.

La función devuelve `True` si `ClassOne` es una subclase de `ClassTwo`, y `False` en caso contrario.

Para ilustrar cómo funciona `issubclass()`, consideremos un ejemplo sencillo que incluye tres clases:

```
class Vehicle:
    pass

class LandVehicle(Vehicle):
    pass

class TrackedVehicle(LandVehicle):
    pass

for cls1 in [Vehicle, LandVehicle, TrackedVehicle]:
    for cls2 in [Vehicle, LandVehicle, TrackedVehicle]:
        print(issubclass(cls1, cls2), end="\t")
    print()
```

Cuando ejecutamos el código anterior, obtenemos la siguiente salida:

```
True	False	False	
True	True	False	
True	True	True	
```
La salida se puede organizar en un formato más legible:

```
↓ es una subclase de → 	Vehicle 	LandVehicle 	TrackedVehicle
Vehicle          	    True      	False         	False
LandVehicle      	    True       	True          	False
TrackedVehicle   	    True       	True          	True
```

Un aspecto clave de la función `issubclass()` es que cada clase se considera una subclase de sí misma. Esto refuerza la idea de que la relación de herencia es transitiva y reflexiva.

