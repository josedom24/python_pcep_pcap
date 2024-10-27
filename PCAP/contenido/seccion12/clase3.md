# Creando generadores

Veamos algunos ejemplo de generadores y del uso que podemos hacer con ellos.

## Ejemplo potencias de 2

Vamos a crear un  un generador para producir las primeras n potencias de 2:

```
def powers_of_2(n):
    power = 1
    for i in range(n):
        yield power
        power *= 2


for v in powers_of_2(8):
    print(v)
```

Podemos usar nuestro generador con una lista por compresión:

```
def powers_of_2(n):
    power = 1
    for i in range(n):
        yield power
        power *= 2


t = [x for x in powers_of_2(5)]
print(t)
```

La función `list()` puede tomar un generador y crear una lista con los elementos devueltos:

```
def powers_of_2(n):
    power = 1
    for i in range(n):
        yield power
        power *= 2


t = list(powers_of_2(3))
print(t)
```

Además, podemos user el operador `in` con un generador:

```
def powers_of_2(n):
    power = 1
    for i in range(n):
        yield power
        power *= 2


for i in range(20):
    if i in powers_of_2(4):
        print(i)
```

## Generador de números Fibonacci

Ahora veamos un generador de números de la serie Fibonacci, asegurandonos que se vea mucho mejor que la versión orientada a objetos basada en la implementación directa del protocolo iterador.

```
def fibonacci(n):
    p = pp = 1
    for i in range(n):
        if i in [0, 1]:
            yield 1
        else:
            n = p + pp
            pp, p = p, n
            yield n

fibs = list(fibonacci(10))
print(fibs)
```
