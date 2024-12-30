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

class Orugas:
    def cambiar_direccion(self, lado, on):
        print("pistas: ", lado, on)

class Ruedas:
    def cambiar_direccion(self, lado, on):
        print("ruedas: ", lado, on)

class Vehiculo:
    def __init__(self, controlador):
        self.controlador = controlador

    def girar(self, lado):
        self.controlador.cambiar_direccion(lado, True)
        time.sleep(0.25)
        self.controlador.cambiar_direccion(lado, False)

# Creamos vehículos con diferentes controladores
vehiculooruga = Vehiculo(Ruedas())
vehiculorueda = Vehiculo(Orugas())

vehiculooruga.girar("Izquierda")  # El vehículo con ruedas gira a la izquierda
vehiculorueda.girar("Derecha")  # El vehículo con orugas gira a la derecha
```

* **Orugas** y **Ruedas**: Estas clases implementan el método `cambiar_direccion()`, que es responsable de controlar el giro del vehículo según sea con orugas o con ruedas.
* **Vehiculo**: Esta clase no implementa directamente el mecanismo de giro. En su lugar, tiene un controlador (`controlador`) que es pasado en su inicialización. Este controlador es un objeto de la clase `Orugas` o `Ruedas`, y el método `girar()` llama a los métodos del controlador correspondiente para realizar el giro.
* **Resultado**: Al crear instancias del vehículo con diferentes controladores (ruedas u orugas), el mismo vehículo puede cambiar su comportamiento sin modificar su estructura interna. La salida muestra cómo cambian los mensajes dependiendo del tipo de controlador asignado al vehículo.

