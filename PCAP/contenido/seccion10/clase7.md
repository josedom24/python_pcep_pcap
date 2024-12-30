# Cómo construir una jerarquía de clases

En este apartado vamos a presentar cómo construir una jerarquía de clases. Para ello partimos de la definición de dos clases de vehículos terrestres, uno con orugas y otro con ruedas. La diferencia principal entre ellos radica en cómo realizan los giros: el vehículo con orugas lo hace deteniendo una de sus pistas, mientras que el vehículo con ruedas gira moviendo sus ruedas delanteras.

En este ejemplo inicial, las dos clases están separadas y no utilizan herencia, lo que resalta que, aunque no siempre es necesario usarla, existe la oportunidad de mejorar el diseño aprovechando este principio. Veamos el código:

```
import time

class VehiculoOruga:
    def control_giro(self, lado, stop):
        print("Pista:", lado, stop)

    def girar(self, lado):
        self.control_giro(lado, True)
        time.sleep(0.25)
        self.control_giro(lado, False)

class VehiculoRueda:
    def girar_ruedas_frontales(self, lado, on):
        print("Rueda:", lado, on)

    def girar(self, lado):
        self.girar_ruedas_frontales(lado, True)
        time.sleep(0.25)
        self.girar_ruedas_frontales(lado, False)
```

* **VehiculoOruga**: Esta clase representa un vehículo con orugas. Realiza el giro controlando sus pistas mediante el método `control_giro()`, que detiene una de las pistas para permitir el giro.
* **VehiculoRueda**: Esta clase representa un vehículo con ruedas, que gira moviendo sus ruedas delanteras usando el método `girar_ruedas_frontales()`.

Ambas clases tienen un método `girar()` que sigue una estructura similar para realizar el giro, lo que indica que hay duplicación de código. El método `girar()` en ambas clases es casi idéntico, lo cual es una clara señal de que **el diseño puede ser optimizado**. En lugar de repetir el mismo código en dos clases diferentes, sería más eficiente crear una **superclase** que encapsule el comportamiento común y dejar los detalles específicos (como la forma en que gira cada vehículo) en las subclases.

## Uso de una superclase

Para mejorar la estructura, se propone la introducción de una superclase que contenga el método `girar()`, centralizando la lógica común. Las subclases se encargarían de implementar los detalles específicos, como el control de las pistas o el movimiento de las ruedas delanteras.

```
import time

class Vehiculo:
    def cambia_direccion(lado, on):
        pass

    def girar(self,lado):
        self.cambia_direccion(lado, True)
        time.sleep(0.25)
        self.cambia_direccion(lado, False)


class VehiculoOruga(Vehiculo):
    def control_giro(self, lado, stop):
        print("Pista:", lado, stop)

    def cambia_direccion(self, lado, on):
        self.control_giro(lado, on)


class VehiculoRueda(Vehiculo):
    def girar_ruedas_frontales(self, lado, on):
        print("Rueda:", lado, on)

    def cambia_direccion(self, lado, on):
        self.girar_ruedas_frontales(lado, on)
```

* Definimos una superclase llamada `Vehiculo`, la cual utiliza el método `girar()` para implementar un esquema para poder girar, mientras que el giro en si es realizado por `cambia_direccion()`; nota: dicho método está vacío, ya que vamos a poner todos los detalles en la subclase (dicho método a menudo se denomina **método abstracto**, ya que solo demuestra alguna posibilidad que será instanciada más tarde).
* Definimos una subclase llamada `VehiculoOruga` (nota: es derivada de la clase `Vehiculo`) la cual instancia el método `cambia_direccion()` utilizando el método denominado `control_giro()`.
* De manera similar, la subclase llamada `VehiculoRueda` hace lo mismo, pero usa el método `girar_ruedas_frontales()` para obligar al vehículo a girar.

La ventaja más importante es que esta forma de código te permite implementar un nuevo algoritmo de giro simplemente modificando el método `girar()`, lo cual se puede hacer en un solo lugar, ya que todos los vehículos lo obedecerán.

Así es como el el **poliformismo** ayuda al desarrollador a mantener el código limpio y consistente.

