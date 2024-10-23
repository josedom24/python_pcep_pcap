# LABORATORIO: Colas alias FIFO: parte 2

## Tiempo Estimado

15 - 30 minutos

## Nivel de Dificultad

Fácil/Medio

## Objetivos

* Mejorar las habilidades del estudiante para definir subclases.
* Agregar nueva funcionalidad a una clase existente.

## Escenario

Tu tarea es extender ligeramente las capacidades de la clase `Queue`. Queremos que tenga un método sin parámetros que devuelva `True` si la cola está vacía y `False` de lo contrario.

Para ello vamos a heredar una subclase.

Puedes usar la siguiente plantilla:

```
class QueueError(???):
    pass


class Queue:
    #
    # Código del laboratorio anterior.
    #


class SuperQueue(Queue):
    #
    # Escribe código nuevo aquí.
    #


que = SuperQueue()
que.put(1)
que.put("perro")
que.put(False)
for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Cola vacía")
```

## Salida Esperada

```
1
perro
False
Cola vacía
```