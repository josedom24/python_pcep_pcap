# Ejemplo 3: El Procesador de Números

El tercer programa muestra un método simple que permite ingresar una línea llena de números y sumarlos fácilmente. Nota: la función `input()`, combinada junto con las funciones `int()` o `float()`, no es lo adecuado para este propósito.

El procesamiento será extremadamente fácil: queremos que se sumen los números.

```
#Procesador de Números.

line = input("Ingresa una línea de números, sepáralos con espacios: ")
strings = line.split()
total = 0
try:
    for substr in strings:
        total += float(substr)
    print("El total es:", total)
except:
    print(substr, "no es un numero.")
```

Emplear listas puede hacer que el código sea más pequeño. Puedes hacerlo si quieres.

Presentemos nuestra versión:

* Pide al usuario que ingrese una línea llena de cualquier cantidad de números (los números pueden ser flotantes).
* Divide la línea en una lista con subcadenas.
* Se inicializa la suma total a cero.
* Como la conversión de cadena a flotante puede generar una excepción, es mejor continuar con la protección del bloque try-except.
* Itera a través de la lista...
* ... e intenta convertir todos sus elementos en números flotantes; si funciona, aumenta la suma.
* Todo está bien hasta ahora, así que imprime la suma.
* El programa termina aquí en caso de error.
* Imprime un mensaje de diagnóstico que muestra al usuario el motivo de la falla.

El código tiene una debilidad importante: muestra un resultado falso cuando el usuario ingresa una línea vacía. ¿Puedes arreglarlo?