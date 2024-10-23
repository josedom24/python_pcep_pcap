# Pila: Enfoque procedimental 

## ¿Qué es una pila?

Una pila es una estructura de datos que sigue el principio de *Último en Entrar, Primero en Salir* (UEPS o LIFO, por sus siglas en inglés: *Last In, First Out*). Imagina una pila de monedas: solo puedes agregar o sacar monedas desde la parte superior. La última moneda en entrar será la primera en salir. En informática, las pilas son esenciales en muchos algoritmos y estructuras. Las **operaciones fundamentales** que podemos realizar sobre una pila son:

* **push**: Añade un elemento a la parte superior de la pila.
* **pop**: Extrae el elemento superior de la pila.

## El enfoque procedimental

El enfoque procedimental utiliza funciones independientes que manejan una lista. El ejemplo muestra este enfoque, donde se usa una lista para almacenar los valores. En este ejemplo, `push` agrega un valor a la pila y `pop` lo elimina y devuelve.

```
stack = []

def push(val):
    stack.append(val)

def pop():
    val = stack[-1]
    del stack[-1]
    return val

push(3)
push(2)
push(1)

print(pop())
print(pop())
print(pop())
```


Que problemas nos encontramos:

1. **Falta de encapsulamiento**: La lista de la pila (`stack`) está expuesta, permitiendo que cualquiera la modifique directamente, lo que puede causar problemas.
2. **Dificultad para manejar múltiples pilas**: Si necesitas más de una pila, debes crear nuevas listas y funciones, lo que incrementa la complejidad.
3. **Ampliación limitada**: Agregar nuevas funcionalidades a la pila puede ser complicado y poco eficiente.

