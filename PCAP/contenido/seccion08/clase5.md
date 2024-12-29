# Pila: Creación de varios objetos

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


## Otro ejemplo

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


little_stack = Stack()
another_stack = Stack()
funny_stack = Stack()

little_stack.push(1)
another_stack.push(little_stack.pop() + 1)
funny_stack.push(another_stack.pop() - 2)

print(funny_stack.pop())
```