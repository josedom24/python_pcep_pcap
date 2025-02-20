# Relación entre objetos y clases

En Python, un objeto es una instancia de una clase, pero en ocasiones necesitamos comprobar de que clase es un objeto. La función `isinstance()` se utiliza para verificar si un objeto es una instancia de una clase determinada o de una de sus subclases. Su sintaxis es la siguiente:

```
isinstance(NombreObjeto, NombreClase)
```

* `NombreObjeto`: El objeto que se está evaluando.
* `NombreClase`: La clase que se considera como posible tipo del objeto.

La función devuelve `True` si `NombreObjeto` es una instancia de `NombreClase` o de una de sus superclases, y `False` en caso contrario.

Consideremos un ejemplo con una jerarquía de clases que incluye `Vehicle`, `LandVehicle` y `TrackedVehicle`:

```
class Vehiculo:
    pass

class VehiculoTerrestre(Vehiculo):
    pass

class VehiculoOruga(VehiculoTerrestre):
    pass

mivehiculo = Vehiculo()
mivehiculoterrestre = VehiculoTerrestre()
mivehiculooruga = VehiculoOruga()

for obj in [mivehiculo, mivehiculoterrestre, mivehiculooruga]:
    for cls in [Vehiculo, VehiculoTerrestre, VehiculoOruga]:
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
↓ es una instancia de → 	Vehiculo 	VehiculoTerrestre 	VehiculoOruga
mivehiculo              	True       	False            	False
mivehiculoterrestre     	True       	True            	False
mivehiculooruga  	        True       	True               	True
```

* **Primera Fila**: `mivehiculo` es una instancia de `Vehiculo` pero no de `VehiculoTerrestre` ni de `VehiculoOruga`.
* **Segunda Fila**: `my_land_vehicle` es una instancia de `Vehicle` y también de `LandVehicle`, pero no de `TrackedVehicle`.
* **Tercera Fila**: `my_tracked_vehicle` es una instancia de `Vehicle`, `LandVehicle` y de sí mismo (`TrackedVehicle`).

La tabla resultante confirma nuestras expectativas sobre la relación entre las clases y sus instancias. La función `isinstance()` permite verificar de manera eficiente si un objeto pertenece a una clase específica o a una jerarquía de clases, asegurando que los comportamientos y características esperados se mantengan.

## Comprobando si dos objetos son iguales

En Python, el operador `is` es una herramienta fundamental para verificar si dos variables apuntan al mismo objeto en la memoria. A diferencia de la comparación de valores, que se realiza con el operador `==`, `is` se centra en la identidad del objeto.

El operador `is` compara dos variables y devuelve `True` si ambas se refieren al mismo objeto en memoria, y `False` si apuntan a objetos diferentes. Es importante recordar que en Python, las variables no almacenan los objetos directamente; en su lugar, mantienen referencias a los objetos en memoria.

Veamos el siguiente ejemplo:

```
class ClaseEjemplo:
    def __init__(self, val):
        self.val = val

objeto1 = ClaseEjemplo(0)
objeto2 = ClaseEjemplo(2)
objeto3 = objeto1
objeto3.val += 1

print(objeto1 is objeto2)  # Comparando objeto1 y objeto2
print(objeto2 is objeto3)  # Comparando objeto2 y objeto3
print(objeto3 is objeto1)  # Comparando objeto3 y objeto1
print(objeto1.val, objeto2.val, objeto3.val)

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


* `objeto1 is objeto2`: `False`, ya que `objeto1` y `objeto2` son instancias diferentes de `ClaseEjemplo`.
* `objeto2 is objeto3`: `False`, porque `objeto2` es un objeto distinto a `objeto3`.
* `objeto3 is objeto1`: `True`, ya que `objeto3` se asignó como referencia a `objeto1`, por lo que ambos apuntan al mismo objeto.
* La impresión de `objeto1.val`, `objeto2.val` y `objeto3.val` muestra `1 2 1`, reflejando el hecho de que al incrementar `objeto3.val`, también se actualizó `objeto1.val` porque son el mismo objeto, mientras que `objeto2.val` permanece en `2`.
* `string_1 == string_2`: `True`, ambas cadenas tienen el mismo contenido.
* `string_1 is string_2`: `False`, aunque contienen el mismo texto, son objetos diferentes en memoria.

