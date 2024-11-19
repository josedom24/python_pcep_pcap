# LABORATORIO - La instrucción continue

## Tiempo Estimado

10 - 15 minutos

## Nivel de Dificultad

Fácil

## Objetivos

Familiarizar al estudiante con:

* Utilizar la instrucción `continue` en los bucles.
* Reflejar situaciones de la vida real en un programa de ordenador.

## Escenario

La instrucción `continue` se usa para omitir el bloque actual y avanzar a la siguiente iteración, sin ejecutar las instrucciones dentro del bucle. Se puede usar tanto con `while` y `for`.

Tu tarea aquí es muy especial: ¡Debes diseñar un devorador de vocales! Escribe un programa que use:

* Un bucle `for`.
* El concepto de ejecución condicional (`if-elif-else`).
* La instrucción `continue`.

Tu programa debe:

* Pedir al usuario que ingrese una palabra.
* Utiliza `palabra_usuario = palabra_usuario.upper()` para convertir la palabra ingresada por el usuario a mayúsculas; hablaremos sobre los llamados métodos de cadena y el método `upper()` muy pronto, no te preocupes.
* Utiliza la ejecución condicional y la instrucción `continue` para "comer" las vocales `A , E , I , O , U` de la palabra ingresada.
* Imprime las letras no consumidas en la pantalla, cada una de ellas en una línea separada.

Prueba tu programa con los datos que le proporcionamos.

Puedes usar esta plantilla:

```
# Indicar al usuario que ingrese una palabra
# y asignarlo a la variable palabra_usuario.

for letra in palabra_usuario:
    # Completa el cuerpo del bucle for.
```

## Datos de Prueba

* Entrada de muestra: `Gregory`
    * Salida esperada:

    ```
    G
    R
    G
    R
    Y
    ```

* Entrada de muestra: `abstemious`
    * Salida esperada:
    
    ```
    B
    S
    T
    M
    S
    ```

* Entrada de muestra: `IOUEA`
    * Salida esperada:


## Mejora

Vamos a mejorar el *Devorador de vocales*. Modifica el programa anterior para que no vaya escribiendo cada letra, sino que las asigne a la variable `palabra_sin_vocales` e imprime la variable en la pantalla.

Utiliza esta plantilla para empezar:

```
palabra_sin_vocales = ""

# Indicar al usuario que ingrese una palabra
# y asignarla a la variable user_word.


for letter in user_word:
   # Completa el cuerpo del bucle.

# Imprimir la palabra asignada a palabra_sin_vocales.
```

Hemos creado `palabra_sin_vocales` y le hemos asignado una cadena vacía. Utiliza la operación de concatenación para pedirle a Python que añada las letras seleccionadas a dicha variable durante los siguientes giros de bucle.

Prueba tu programa con los datos que le proporcionamos.

## Datos de Prueba

* Entrada de muestra: `Gregory`
    * Salida esperada: `GRGRY`

* Entrada de muestra: `abstemious`
    * Salida esperada: `BSTMS`

* Entrada de muestra: `IOUEA`
    * Salida esperada: 
