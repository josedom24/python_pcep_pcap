# Las instrucciones break y continue

Hasta ahora, hemos tratado el cuerpo del bucle como una secuencia indivisible e inseparable de instrucciones que se realizan completamente en cada giro del bucle. Sin embargo, como desarrollador, podrías enfrentar las siguientes opciones:

* Parece que **no es necesario continuar el bucle** en su totalidad; se debe parar de seguir ejecutando el cuerpo del bucle y ejecutar la siguiente instrucción.
* Parece que **necesitas comenzar el siguiente giro del bucle sin completar la ejecución del turno actual**.

Python proporciona dos instrucciones especiales para la implementación de estas dos tareas. Digamos por razones de precisión que su existencia en el lenguaje no es necesaria: un programador experimentado puede codificar cualquier algoritmo sin estas instrucciones. Tales adiciones, que no mejoran el poder expresivo del lenguaje, sino que solo simplifican el trabajo del desarrollador, a veces se denominan dulces sintácticos o azúcar sintáctica.

Estas dos instrucciones son:

* `break`: sale del bucle inmediatamente, e incondicionalmente termina la operación del bucle; el programa comienza a ejecutar la instrucción más cercana después del cuerpo del bucle.
* `continue`: se comporta como si el programa hubiera llegado repentinamente al final del cuerpo; el siguiente turno se inicia y la expresión de condición se prueba de inmediato.

Ambas palabras son palabras clave reservadas.

## Ejemplo 1

Ahora te mostraremos dos ejemplos simples para ilustrar como funcionan las dos instrucciones. 

```
# break - ejemplo

print("La instrucción break:")
for i in range(1, 6):
    if i == 3:
        break
    print("Dentro del bucle.", i)
print("Fuera del bucle.")


# continue - ejemplo

print("\nLa instrucción continue:")
for i in range(1, 6):
    if i == 3:
        continue
    print("Dentro del bucle.", i)
print("Fuera del bucle.")
```

## Ejemplo 2

Veamos un ejemplo con `break`:

```
secreto = "asdasd"
clave = input("Dime la clave:")
while clave != secreto:
    print("Clave incorrecta!!!")
    otra = input("¿Quieres introducir otra clave (S/N)?:")
    if otra.upper()=="N":
        break;
    clave = input("Dime la clave:")
if clave == secreto:
    print("Bienvenido!!!")
print("Programa terminado")
```

Cuando se introduce `N` para indicar que no queremos indicar otra calve, el bucle termina.

## Ejemplo 3

Podemos usar la instrucción `continue` en el siguiente ejemplo para mostrar los números pares del 1 al 10:

```
# Con while
cont = 0
while cont<10:
    cont = cont + 1
    if cont % 2 != 0:
        continue
    print(cont)

# Con for
for cont in range(1,11):
    if cont % 2 != 0:
        continue
    print(cont)