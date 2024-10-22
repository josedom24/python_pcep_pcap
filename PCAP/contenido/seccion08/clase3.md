# Pila: Programación orientada a objetos

Para empezar, creamos una clase llamada `Stack`. Esta clase actuará como la estructura de nuestra pila:

```
class Stack:
    pass
```

## Propiedades de la clase

Usaremos **una lista como el mecanismo de almacenamiento de la pila**. Sin embargo, necesitamos asegurarnos de que cada objeto de la clase `Stack` tenga su propia lista, no una lista compartida. Además, la lista debe estar oculta del acceso directo de los usuarios de la clase.

Por lo tanto **la clase tendrá una propiedad que será la lista donde guardamos los elementos de la pila**.

## El método constructor de la clase

En Python, no se declaran explícitamente las propiedades como en otros lenguajes. En su lugar, usamos un **constructor**, que es un método especial llamada automáticamente cuando se crea un nuevo objeto. Esta función tiene el nombre reservado `__init__` y sirve para inicializar las propiedades de cada objeto de la clase.

Ejemplo de un constructor simple:

```
class Stack:
    def __init__(self):
        print("¡Hola!")
```

Cuando creamos un objeto de la clase `Stack`, el constructor es llamado automáticamente:

```
stack_object = Stack()
```

La salida será `¡Hola!`.


Debemos tener en cuenta a la hora de crear el constructor:

* El constructor siempre se llama `__init__`.
* El primer parámetro del constructor siempre es `self`, que representa al objeto que se está creando. A través de `self`, se pueden agregar propiedades al objeto y manipular su contenido.
* Aunque `self` es solo una convención, es ampliamente usada y recomendada.

Este enfoque nos permite encapsular la estructura y comportamiento de la pila dentro de una clase, ocultando los detalles de implementación y manteniendo el control sobre las interacciones con la pila.

Para continuar con el enfoque orientado a objetos de la pila en Python, vamos a revisar algunos puntos clave de la implementación actual y cómo podemos mejorarla.

## El método constructor de nuestra pila

Para implementar nuestra calse `Stack` vamos a añadir una propiedad llamada `stack_list` dentro del constructor, que se inicializa como una lista vacía. Esto permite que cada objeto de la clase `Stack` tenga su propia lista donde se almacenarán los elementos de la pila:

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

## Ejemplo de uso de la pila

Aquí creamos un objeto de la clase `Stack` y usamos los métodos `push` y `pop` para interactuar con la pila:

```
stack_object = Stack()

# Agregamos elementos a la pila
stack_object.push(3)
stack_object.push(2)
stack_object.push(1)

# Quitamos y mostramos los elementos de la pila
print(stack_object.pop())  # Output: 1
print(stack_object.pop())  # Output: 2
print(stack_object.pop())  # Output: 3
```

Cuando invocamos `stack_object.push(3)`, el proceso interno es el siguiente:
1. Python envía implícitamente el objeto `stack_object` como el argumento `self` al método `push`.
2. Dentro de `push`, `self.__stack_list.append(val)` añade el valor `3` a la lista privada `__stack_list`.

De manera similar, el método `pop` quita el último valor de la lista y lo retorna.


## Creación de varios objetos pila

Ahora puedes hacer que más de una pila se comporte de la misma manera. Cada pila tendrá su propia copia de datos privados, pero utilizará el mismo conjunto de métodos. 

Analicemos el código de ejemplo que muestra cómo funcionan dos objetos de la clase `Stack` de manera independiente:

```
class Stack:
    def __init__(self):
        self.__stack_list = []  # Lista privada para cada pila

    # Método para agregar un valor a la pila
    def push(self, val):
        self.__stack_list.append(val)

    # Método para quitar y devolver el último valor de la pila
    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


# Creación de dos objetos de la clase Stack
stack_object_1 = Stack()
stack_object_2 = Stack()

# Operaciones con ambas pilas
stack_object_1.push(3)  # Añade el valor 3 a la primera pila
stack_object_2.push(stack_object_1.pop())  # Pasa el valor de la primera pila a la segunda

# Muestra el valor de la segunda pila
print(stack_object_2.pop())  # Output: 3
```

* Se crean **dos pilas** diferentes: `stack_object_1` y `stack_object_2`. Ambas se basan en la misma clase `Stack`, pero son **objetos independientes**.
* Cada uno tiene su propia lista privada (`__stack_list`), lo que significa que las operaciones realizadas en una pila no afectan a la otra.

Veamos qué hace cada instrucción:

1. **`stack_object_1.push(3)`**: Añade el valor `3` a la primera pila (`stack_object_1`).
   
2. **`stack_object_2.push(stack_object_1.pop())`**:
   * Primero, **`stack_object_1.pop()`** quita y retorna el valor `3` de la primera pila.
   * Luego, este valor es pasado como argumento al método **`stack_object_2.push(3)`**, que añade `3` a la segunda pila (`stack_object_2`).
3. **`print(stack_object_2.pop())`**: Finalmente, se quita y muestra el valor `3` de la segunda pila.



























El enfoque orientado a objetos resuelve los problemas anteriores mediante:
* **Encapsulamiento**: Los datos internos de la pila están protegidos y no pueden modificarse directamente.
* **Herencia**: Puedes crear clases derivadas para ampliar las funcionalidades sin modificar la clase base.

Veamos el ejemplo de creación de la clase:

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
```

En este ejemplo:
- **Encapsulamiento**: La lista de la pila (`__stack_list`) está oculta, y solo los métodos `push` y `pop` pueden modificarla.
- **Múltiples instancias**: Puedes crear tantas pilas como quieras, cada una con su propia lista de almacenamiento.

---

## 3.2.4 Ampliación con herencia: `AddingStack`

La herencia permite crear una subclase que extienda la funcionalidad de la pila sin modificar la clase base.

### Ejemplo: Pila que suma los elementos

```
class AddingStack(Stack):
    def __init__(self):
        super().__init__()
        self.__sum = 0

    def push(self, val):
        self.__sum += val
        super().push(val)

    def pop(self):
        val = super().pop()
        self.__sum -= val
        return val

    def get_sum(self):
        return self.__sum
```

Aquí, `AddingStack`:
- **Hereda** de `Stack` y reutiliza sus métodos.
- **Agrega funcionalidad**: Mantiene la suma de todos los elementos y permite consultarla con `get_sum()`.

---

## 3.2.5 Resumen del enfoque OO
1. **Encapsulamiento**: Protege los datos de la pila.
2. **Herencia**: Facilita la extensión de funcionalidades.
3. **Múltiples pilas**: Cada instancia de la clase es independiente y permite trabajar con varias pilas a la vez.

El enfoque orientado a objetos mejora la organización y el control sobre las pilas, permitiendo construir sistemas más robustos y flexibles.