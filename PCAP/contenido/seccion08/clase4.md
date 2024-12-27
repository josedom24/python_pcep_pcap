# Pila: Programación orientada a objetos

En este apartado vamos a crear una clase llamada `Stack`. Esta clase actuará como la estructura de nuestra pila:

## Propiedades de la clase

Usaremos **una lista como el mecanismo de almacenamiento de la pila**. Sin embargo, necesitamos asegurarnos de que cada objeto de la clase `Stack` tenga su propia lista, no una lista compartida. Además, la lista debe estar oculta del acceso directo de los usuarios de la clase.

Por lo tanto **la clase tendrá una propiedad que será la lista donde guardamos los elementos de la pila**.

## El método constructor de la clase

En Python, no se declaran explícitamente las propiedades como en otros lenguajes. En su lugar, usamos un **constructor**, que es un método especial llamada automáticamente cuando se crea un nuevo objeto. Esta función tiene el nombre reservado `__init__` y sirve para inicializar las propiedades de cada objeto de la clase.

Debemos tener en cuenta a la hora de crear el constructor:

* El constructor siempre se llama `__init__`.
* El primer parámetro del constructor siempre es `self`, que representa al objeto que se está creando. A través de `self`, se pueden agregar propiedades al objeto y manipular su contenido.
* Aunque `self` es solo una convención, es ampliamente usada y recomendada.

Este enfoque nos permite encapsular la estructura y comportamiento de la pila dentro de una clase, ocultando los detalles de implementación y manteniendo el control sobre las interacciones con la pila.

Para implementar nuestra clase `Stack` vamos a añadir una propiedad llamada `stack_list` dentro del constructor, que se inicializa como una lista vacía. Esto permite que cada objeto de la clase `Stack` tenga su propia lista donde se almacenarán los elementos de la pila:

```
class Stack:
    def __init__(self):
        self.stack_list = []

# Crear un objeto de la clase Stack
stack_object = Stack()

# Comprobar la longitud de la pila
print(len(stack_object.stack_list))  # Output: 0
```

* Usamos **notación punteada** para acceder a las propiedades del objeto. En este caso, `stack_list` se accede con `stack_object.stack_list`, lo que imprime la longitud actual de la lista (0 en este caso, ya que la lista está vacía al crear la pila).
* Normalmente que remos ocultar las propiedades. No queremos que los usuarios puedan acceder directamente a `stack_list`. En Python, podemos ocultar (o "privatizar") una propiedad añadiendo **dos guiones bajos** (`__`) antes del nombre de la propiedad. Esto le indica al intérprete de Python que la propiedad no debería ser accesible directamente desde fuera de la clase.

Modifiquemos la clase para ocultar la propiedad:

```
class Stack:
    def __init__(self):
        self.__stack_list = []

stack_object = Stack()

# Intentar acceder a la lista desde fuera de la clase
# print(len(stack_object.__stack_list))  # Esto dará error
```

Si intentas acceder a `__stack_list` directamente desde fuera de la clase, obtendrás un error, lo que demuestra que la propiedad ahora está oculta. Así es como Python implementa el concepto de **encapsulación**.

## Más métodos de la pila

Ahora que hemos llegado a la parte donde implementamos las operaciones fundamentales de una pila —**push** y **pop**— en una clase orientada a objetos, veamos en detalle cómo funcionan y por qué son necesarias ciertas características del código.

La pila se caracteriza por dos operaciones principales:
* **push**: Añade un elemento al final de la pila.
* **pop**: Elimina el último elemento añadido (en la parte superior de la pila) y lo devuelve.

Aquí está el código completo con las operaciones `push` y `pop` implementadas:

```
class Stack:
    def __init__(self):
        self.__stack_list = []  # Lista privada para almacenar los elementos de la pila

    # Método para agregar un valor a la pila
    def push(self, val):
        self.__stack_list.append(val)

    # Método para quitar y devolver el valor en la parte superior de la pila
    def pop(self):
        val = self.__stack_list[-1]  # Obtiene el último elemento
        del self.__stack_list[-1]    # Elimina el último elemento
        return val
```

* **push(self, val)**: Este método toma un valor `val` y lo añade a la lista privada `__stack_list`. Para ello, accedemos a la lista usando `self.__stack_list` y usamos el método `append()` de las listas de Python.
  
* **pop(self)**: Este método obtiene y elimina el último valor de la lista, que corresponde al valor en la parte superior de la pila. Para acceder al último valor, usamos `self.__stack_list[-1]`, que es la sintaxis para obtener el último elemento de una lista. Luego, lo eliminamos con `del self.__stack_list[-1]` y retornamos el valor.
* **`self` es esencial**: Como en el constructor, todos los métodos de la clase deben tener `self` como el primer parámetro. Este parámetro se utiliza para acceder a las propiedades y otros métodos del objeto.
  * Cuando invocas un método, Python pasa implícitamente el objeto actual como el primer argumento. Esto es lo que permite que el método acceda a `self.__stack_list` y otras propiedades del objeto.
