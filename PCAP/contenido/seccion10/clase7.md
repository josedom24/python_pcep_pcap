# Cómo construir una jerarquía de clases

En este apartado vamos a presentar cómo construir una jerarquía de clases. Para ello partimos de la definición de dos clases de vehículos  terrestres, uno con orugas y otro con ruedas. La diferencia principal entre ellos radica en cómo realizan los giros: el vehículo con orugas lo hace deteniendo una de sus pistas, mientras que el vehículo con ruedas gira moviendo sus ruedas delanteras.

En este ejemplo inicial, las dos clases están separadas y no utilizan herencia, lo que resalta que, aunque no siempre es necesario usarla, existe la oportunidad de mejorar el diseño aprovechando este principio. Veamos el código:

```
import time

class TrackedVehicle:
    def control_track(self, left, stop):
        pass

    def turn(self, left):
        self.control_track(left, True)
        time.sleep(0.25)
        self.control_track(left, False)

class WheeledVehicle:
    def turn_front_wheels(self, left, on):
        pass

    def turn(self, left):
        self.turn_front_wheels(left, True)
        time.sleep(0.25)
        self.turn_front_wheels(left, False)
```

* **TrackedVehicle**: Esta clase representa un vehículo con orugas. Realiza el giro controlando sus pistas mediante el método `control_track()`, que detiene una de las pistas para permitir el giro.
* **WheeledVehicle**: Esta clase representa un vehículo con ruedas, que gira moviendo sus ruedas delanteras usando el método `turn_front_wheels()`.

Ambas clases tienen un método `turn()` que sigue una estructura similar para realizar el giro, lo que indica que hay duplicación de código. El método `turn()` en ambas clases es casi idéntico, lo cual es una clara señal de que **el diseño puede ser optimizado**. En lugar de repetir el mismo código en dos clases diferentes, sería más eficiente crear una **superclase** que encapsule el comportamiento común y dejar los detalles específicos (como la forma en que gira cada vehículo) en las subclases.

## Uso de una superclase

Para mejorar la estructura, se propone la introducción de una superclase que contenga el método `turn()`, centralizando la lógica común. Las subclases se encargarían de implementar los detalles específicos, como el control de las pistas o el movimiento de las ruedas delanteras.

```
import time

class Vehicle:
    def change_direction(left, on):
        pass

    def turn(left):
        change_direction(left, True)
        time.sleep(0.25)
        change_direction(left, False)


class TrackedVehicle(Vehicle):
    def control_track(left, stop):
        pass

    def change_direction(left, on):
        control_track(left, on)


class WheeledVehicle(Vehicle):
    def turn_front_wheels(left, on):
        pass

    def change_direction(left, on):
        turn_front_wheels(left, on)
```

* Definimos una superclase llamada `Vehicle`, la cual utiliza el método `turn()` para implementar un esquema para poder girar, mientras que el giro en si es realizado por `change_direction()`; nota: dicho método está vacío, ya que vamos a poner todos los detalles en la subclase (dicho método a menudo se denomina **método abstracto**, ya que solo demuestra alguna posibilidad que será instanciada más tarde).
* Definimos una subclase llamada `TrackedVehicle` (nota: es derivada de la clase `Vehicle`) la cual instancia el método `change_direction()` utilizando el método denominado `control_track()`.
* De manera similar, la subclase llamada `WheeledVehicle` hace lo mismo, pero usa el método `turn_front_wheels()` para obligar al vehículo a girar.

La ventaja más importante es que esta forma de código te permite implementar un nuevo algoritmo de giro simplemente modificando el método `turn()`, lo cual se puede hacer en un solo lugar, ya que todos los vehículos lo obedecerán.

Así es como el el **poliformismo** ayuda al desarrollador a mantener el código limpio y consistente.

