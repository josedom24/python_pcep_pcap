# Ejemplos de generadores

Veamos algunos ejemplo de generadores y del uso que podemos hacer con ellos.

## Ejemplo potencias de 2

Vamos a crear un  un generador para producir las primeras n potencias de 2:

```
def potencia_de_2(n):
    resultado = 1
    for i in range(n):
        yield resultado
        resultado *= 2


for v in potencia_de_2(8):
    print(v)
```

Podemos usar nuestro generador con una lista por compresión:

```
def potencia_de_2(n):
    resultado = 1
    for i in range(n):
        yield resultado
        resultado *= 2


t = [x for x in potencia_de_2(5)]
print(t)
```

La función `list()` puede tomar un generador y crear una lista con los elementos devueltos:

```
def potencia_de_2(n):
    resultado = 1
    for i in range(n):
        yield resultado
        resultado *= 2


t = list(potencia_de_2(3))
print(t)
```

Además, podemos user el operador `in` con un generador:

```
def potencia_de_2(n):
    resultado = 1
    for i in range(n):
        yield resultado
        resultado *= 2


for i in range(20):
    if i in potencia_de_2(4):
        print(i)
```

## Generador de números Fibonacci

Ahora veamos un generador de números de la serie Fibonacci, asegurándonos que se vea mucho mejor que la versión orientada a objetos basada en la implementación directa del protocolo iterador.

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
