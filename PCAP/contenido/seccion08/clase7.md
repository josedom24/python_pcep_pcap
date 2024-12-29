# LABORATORIO: Pila Contadora

## Tiempo Estimado

20 - 45 minutos

## Nivel de Dificultad

Fácil/Medio

## Objetivos

* Mejorar las habilidades del estudiante para definir clases.
* Emplear clases existentes para crear nuevas clases equipadas con nuevas funcionalidades.

## Escenario

Recientemente te mostramos cómo extender las posibilidades de `Stack` definiendo una nueva clase (es decir, una subclase) que retiene todos los rasgos heredados y agrega algunos nuevos.

Tu tarea es extender el comportamiento de la clase `Stack` de tal manera que la clase pueda contar todos los elementos que son agregados (push) y quitados (pop). Emplea la clase `Stack` que proporcionamos en el siguiente código:

```
class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
    #
    # Llena el constructor con acciones apropiadas.
    #

    def get_counter(self):
    #
    # Presenta el valor actual del contador al mundo.
    #

    def pop(self):
    #
    # Haz un pop y actualiza el contador.
    #
	

stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())
```

Sigue las sugerencias:

* Introduce una propiedad diseñada para contar las operaciones `pop` y nombrarla de una manera que garantice que esté oculta.
* Inicialízala a cero dentro del constructor.
* Proporciona un método que devuelva el valor asignado actualmente al contador (nómbralo `get_counter()`).

Completa el código en el editor. Ejecútalo para comprobar si tu código da como salida 100.
