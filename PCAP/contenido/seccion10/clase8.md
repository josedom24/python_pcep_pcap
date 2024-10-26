# Composición

Aunque la herencia es una técnica común para diseñar clases en programación orientada a objetos, no es la única forma de hacer que las clases sean adaptables y flexibles. Existe otra técnica llamada **composición**, que se basa en ensamblar objetos más complejos a partir de otros más simples, dotando a las clases de comportamientos mediante la inclusión de otros objetos.

Veamos las diferencias:

* **Herencia**: Extiende las capacidades de una clase agregando o modificando componentes heredados de otras clases. Toda la lógica de la clase y sus ancestros está contenida en una jerarquía, permitiendo que el objeto use y modifique todos los componentes heredados.
* **Composición**: En lugar de heredar características, una clase "compone" su comportamiento al contener otros objetos que implementan parte de la funcionalidad. Estos objetos actúan como bloques de construcción para crear comportamientos más complejos.

## Ejemplo

En el enfoque basado en herencia, las clases derivadas (como vehículos con ruedas o vehículos con orugas) implementaban el mecanismo específico para girar. Sin embargo, con composición, un **vehículo** delega la acción de girar a un **controlador** externo que sabe cómo manejar la dirección, permitiendo que el mismo vehículo pueda usar diferentes controladores, ya sea de ruedas o de pistas.

Esto introduce un diseño más flexible, donde el vehículo es capaz de interactuar con cualquiera de los controladores disponibles, haciéndolo más adaptable a futuros cambios sin necesidad de modificar la clase principal.

```
import time

class Tracks:
    def change_direction(self, left, on):
        print("pistas: ", left, on)

class Wheels:
    def change_direction(self, left, on):
        print("ruedas: ", left, on)

class Vehicle:
    def __init__(self, controller):
        self.controller = controller

    def turn(self, left):
        self.controller.change_direction(left, True)
        time.sleep(0.25)
        self.controller.change_direction(left, False)

# Creamos vehículos con diferentes controladores
wheeled = Vehicle(Wheels())
tracked = Vehicle(Tracks())

wheeled.turn(True)  # El vehículo con ruedas gira a la izquierda
tracked.turn(False)  # El vehículo con orugas gira a la derecha
```

* **Tracks** y **Wheels**: Estas clases implementan el método `change_direction()`, que es responsable de controlar el giro del vehículo según sea con orugas o con ruedas.
* **Vehicle**: Esta clase no implementa directamente el mecanismo de giro. En su lugar, tiene un controlador (`controller`) que es pasado en su inicialización. Este controlador es un objeto de la clase `Tracks` o `Wheels`, y el método `turn()` llama a los métodos del controlador correspondiente para realizar el giro.
* **Resultado**: Al crear instancias del vehículo con diferentes controladores (ruedas u orugas), el mismo vehículo puede cambiar su comportamiento sin modificar su estructura interna. La salida muestra cómo cambian los mensajes dependiendo del tipo de controlador asignado al vehículo.

