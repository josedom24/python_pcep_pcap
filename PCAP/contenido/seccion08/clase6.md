# Pila: Herencia de clases

Ahora queremos crear una nueva clase para manejar pilas. La nueva clase debería poder evaluar la suma de todos los elementos almacenados actualmente en la pila.

Nos proponemos agregar capacidades adicionales sin modificar la clase original `Stack`, lo que nos lleva la utilización de **herencia** para crear una subclase llamada `AddingStack`.

## Creando la Subclase

El primer paso para implementar la nueva funcionalidad es definir la subclase `AddingStack`, que hereda de la clase `Stack`. La sintaxis es sencilla:

```
class AddingStack(Stack):
    pass
```

En este punto, la clase `AddingStack` no contiene componentes adicionales, pero hereda todos los atributos y métodos de su superclase `Stack`. Esto significa que puede utilizar las funcionalidades básicas de la pila original sin necesidad de duplicar código.

Vamos a añadir nueva funcionalidades a la nueva clase: debe calcular la suma de todos los elementos almacenados en la pila. Para ello:

* Necesitamos otra propiedad para `sum` para guardar la suma.
* El método `push` no solo debe insertar un valor en la pila, sino que también lo debe sumar al nuevo atributo `sum`. 
* El método `pop` debería restar el valor extraído de esta variable.

## Añadiendo un nua nueva propiedad privada

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

Una vez que hemos establecido la estructura básica de `AddingStack`, el siguiente paso es redefinir los métodos `push` y `pop` para que actualicen el atributo `__sum` en consecuencia.

Aquí hay un ejemplo de cómo se verían estos métodos:

```
class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0

    def push(self, val):
        super().push(val)  # Llama al método push de la superclase
        self.__sum += val  # Suma el valor al atributo __sum

    def pop(self):
        val = super().pop()  # Llama al método pop de la superclase
        self.__sum -= val  # Resta el valor del atributo __sum
        return val
```

