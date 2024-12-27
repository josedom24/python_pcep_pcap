# Pila: Herencia de clases

Ahora queremos crear una nueva clase para manejar pilas. La nueva clase debería poder evaluar la suma de todos los elementos almacenados actualmente en la pila.

Nos proponemos agregar capacidades adicionales sin modificar la clase original `Stack`, lo que nos lleva la utilización de **herencia** para crear una subclase llamada `AddingStack`.

## Creando la Subclase

El primer paso para implementar la nueva funcionalidad es definir la subclase `AddingStack`, que hereda de la clase `Stack`. La sintaxis es sencilla:

```
class AddingStack(Stack):
    pass
```

En este punto, la clase `AddingStack` no contiene componentes adicionales, pero hereda todos los atributos y métodos de su superclase `Stack`. Esto significa que puede utilizar las funcionalidades básicas de la pila original sin necesidad de duplicar código. Podríamos crear una objeto a partir de esta clase y comprobar que funciona igual que la clase `Stack`.

Vamos a añadir nueva funcionalidades a la nueva clase: debe calcular la suma de todos los elementos almacenados en la pila. Para ello:

* Necesitamos otra propiedad para `sum` para guardar la suma.
* El método `push` no solo debe insertar un valor en la pila, sino que también lo debe sumar al nuevo atributo `sum`. 
* El método `pop` debería restar el valor extraído de esta variable.

## Añadiendo una nueva propiedad privada

Para lograr esto, comenzaremos por añadir un atributo privado en la nueva clase. Este atributo, llamado `__sum`, almacenará el total de todos los valores de la pila. La implementación del constructor (`__init__`) de la subclase se verá así:

```
class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)  # Inicializa el constructor de la superclase
        self.__sum = 0  # Atributo privado para almacenar la suma
```

## Importancia de invocar el constructor de la superclase

La línea `Stack.__init__(self)` es crucial. En Python, a diferencia de otros lenguajes de programación, es necesario invocar explícitamente el constructor de la superclase para garantizar que el objeto tenga acceso a la lista de la pila (`__stack_list`). Si se omite esta línea, el objeto `AddingStack` no funcionará correctamente, ya que carecerá de la lista necesaria para almacenar los elementos.

Es importante seguir una sintaxis clara al invocar el constructor:

1. Especificar el nombre de la superclase.
2. Añadir un punto (.) seguido del nombre del constructor.
3. Pasar la instancia de la clase actual (`self`) al constructor de la superclase.

Como regla general, se recomienda invocar el constructor de la superclase antes de cualquier otra inicialización en la subclase.

## Implementación de los métodos `push` y `pop`

¿Realmente estamos agregando dos nuevos métodos? Realmente, ya tenemos estos métodos en la superclase. Lo que estamos haciendo es cambiar la funcionalidad de los métodos, no sus nombres. Podemos decir con mayor precisión que la interfaz (la forma en que se manejan los objetos) de la clase permanece igual al cambiar la implementación al mismo tiempo.

Vamos a redefinir los métodos `push` y `pop` para que actualicen el atributo `__sum` en consecuencia.

Aquí hay un ejemplo de cómo se verían estos métodos:

```
class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0

    def push(self, val):
        Stack.push(val)  # Llama al método push de la superclase
        self.__sum += val  # Suma el valor al atributo __sum

    def pop(self):
        val = Stack.pop()  # Llama al método pop de la superclase
        self.__sum -= val  # Resta el valor del atributo __sum
        return val
```

Fíjate en cómo hemos invocado la implementación anterior del método `push` (el disponible en la superclase):

* Tenemos que especificar el nombre de la superclase; esto es necesario para indicar claramente la clase que contiene el método, para evitar confundirlo con cualquier otra función del mismo nombre.
* Tenemos que especificar el objeto de destino y pasarlo como primer argumento (no se agrega implícitamente a la invocación en este contexto).

Se dice que el método `push` ha sido anulado, el mismo nombre que en la superclase ahora representa una funcionalidad diferente.

## Métodos para obtener valores

Hasta ahora, hemos definido la variable `__sum`, pero no hemos proporcionado un método para obtener su valor. Tenemos que definir un nuevo método. Lo nombraremos get_sum. Su única tarea será devolver el valor de `__sum`.

Aquí está:
```
def get_sum(self):
    return self.__sum
```

Veamos el ejemplo completo:

```
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0

    def get_sum(self):
        return self.__sum

    def push(self, val):
        self.__sum += val
        Stack.push(self, val)

    def pop(self):
        val = Stack.pop(self)
        self.__sum -= val
        return val


stack_object = AddingStack()

for i in range(5):
    stack_object.push(i)
print(stack_object.get_sum())

for i in range(5):
    print(stack_object.pop())
```

## Cuestionario

1. Suponiendo que hay una clase llamada `Snakes`, escribe la primera línea de la declaración de una clase llamada `Python`, expresando el hecho de que la nueva clase es en realidad una subclase de `Snakes`.

2. Algo falta en la siguiente declaración, ¿qué es?
    ```
    class Snakes
        def __init__():
            self.sound = 'Sssssss'
    ```



3. Modifica el código para garantizar que la propiedad `venomous` sea privada.
    ```
    class Snakes
        def __init__(self):
            self.venomous = True
    ```

## Solución cuestionario

1. Ejercicio 1

    `class Python(Snakes):`

2. Ejercicio 2

    El constructor `__init__()` carece del parámetro obligatorio (deberíamos llamarlo `self` para cumplir con los estándares).

3. Ejercicio 3

    El código debería verse como sigue:
    ```
    class Snakes
        def __init__(self):
            self.__venomous = True
    ```