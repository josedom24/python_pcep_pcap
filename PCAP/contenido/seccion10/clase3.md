# Relación entre objetos y clases

En Python, un objeto es la encarnación de una clase, pero en ocasiones necesitamos comprobar de que clase es un objeto. La función `isinstance()` se utiliza para verificar si un objeto es una instancia de una clase determinada o de una de sus subclases. Su sintaxis es la siguiente:

```
isinstance(objectName, ClassName)
```

* `objectName`: El objeto que se está evaluando.
* `ClassName`: La clase que se considera como posible tipo del objeto.

La función devuelve `True` si `objectName` es una instancia de `ClassName` o de una de sus subclases, y `False` en caso contrario.

Consideremos un ejemplo con una jerarquía de clases que incluye `Vehicle`, `LandVehicle` y `TrackedVehicle`:

```
class Vehicle:
    pass

class LandVehicle(Vehicle):
    pass

class TrackedVehicle(LandVehicle):
    pass

my_vehicle = Vehicle()
my_land_vehicle = LandVehicle()
my_tracked_vehicle = TrackedVehicle()

for obj in [my_vehicle, my_land_vehicle, my_tracked_vehicle]:
    for cls in [Vehicle, LandVehicle, TrackedVehicle]:
        print(isinstance(obj, cls), end="\t")
    print()
```

Al ejecutar el código anterior, obtenemos la siguiente salida:

```
True	False	False	
True	True	False	
True	True	True	
```

Podemos organizar la salida en una tabla más legible:

```
↓ es una instancia de → 	Vehicle 	LandVehicle 	TrackedVehicle
my_vehicle          	True         	False         	False
my_land_vehicle     	True         	True          	False
my_tracked_vehicle  	True         	True          	True
```

* **Primera Fila**: `my_vehicle` es una instancia de `Vehicle` pero no de `LandVehicle` ni de `TrackedVehicle`.
* **Segunda Fila**: `my_land_vehicle` es una instancia de `Vehicle` y también de `LandVehicle`, pero no de `TrackedVehicle`.
* **Tercera Fila**: `my_tracked_vehicle` es una instancia de `Vehicle`, `LandVehicle` y de sí mismo (`TrackedVehicle`).

La tabla resultante confirma nuestras expectativas sobre la relación entre las clases y sus instancias. La función `isinstance()` permite verificar de manera eficiente si un objeto pertenece a una clase específica o a una jerarquía de clases, asegurando que los comportamientos y características esperados se mantengan.

## Comprobando si dos objetos son iguales

En Python, el operador `is` es una herramienta fundamental para verificar si dos variables apuntan al mismo objeto en la memoria. A diferencia de la comparación de valores, que se realiza con el operador `==`, `is` se centra en la identidad del objeto.

El operador `is` compara dos variables y devuelve `True` si ambas se refieren al mismo objeto en memoria, y `False` si apuntan a objetos diferentes. Es importante recordar que en Python, las variables no almacenan los objetos directamente; en su lugar, mantienen referencias a los objetos en memoria.

Veamos el siguiente ejemplo:

```
class SampleClass:
    def __init__(self, val):
        self.val = val

object_1 = SampleClass(0)
object_2 = SampleClass(2)
object_3 = object_1
object_3.val += 1

print(object_1 is object_2)  # Comparando object_1 y object_2
print(object_2 is object_3)  # Comparando object_2 y object_3
print(object_3 is object_1)  # Comparando object_3 y object_1
print(object_1.val, object_2.val, object_3.val)

string_1 = "Mary tenía un "
string_2 = "Mary tenía un corderito"
string_1 += "corderito"

print(string_1 == string_2, string_1 is string_2)  # Comparación de cadenas
```

Al ejecutar el código anterior, obtendremos la siguiente salida:

```
False
False
True
1 2 1
True False
```


* `object_1 is object_2`: `False`, ya que `object_1` y `object_2` son instancias diferentes de `SampleClass`.
* `object_2 is object_3`: `False`, porque `object_2` es un objeto distinto a `object_3`.
* `object_3 is object_1`: `True`, ya que `object_3` se asignó como referencia a `object_1`, por lo que ambos apuntan al mismo objeto.
* La impresión de `object_1.val`, `object_2.val` y `object_3.val` muestra `1 2 1`, reflejando el hecho de que al incrementar `object_3.val`, también se actualizó `object_1.val` porque son el mismo objeto, mientras que `object_2.val` permanece en `2`.
* `string_1 == string_2`: `True`, ambas cadenas tienen el mismo contenido.
* `string_1 is string_2`: `False`, aunque contienen el mismo texto, son objetos diferentes en memoria.

