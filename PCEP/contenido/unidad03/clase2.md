# Literales numéricos

## Literales enteros

Python entiende que un número es entero como un conjunto de dígitos sin ningún otro signo diferente a un número. Si queremos representar el número *once millones ciento once mil ciento once*, para Python la forma correcta sería `11111111`. Nosotros podríamos representarlos cómo: `11,111,111`, o así: `11.111.111`, incluso de esta manera: `11 111 111`, pero todas estas formas serían erróneas para Python.

Es claro que la separación hace que sea más fácil de leer, especialmente cuando el número tiene demasiados dígitos. Python permite el uso de guion bajo en los literales numéricos.

Por lo tanto, el número se puede escribir ya sea así: `11111111`, o como sigue: `11_111_111`. Está última forma se puede hacer desde la versión 2.6 de Python para mejorar la legibilidad.

¿Cómo se codifican los números negativos en Python? Como normalmente se hace, agregando un signo de menos. Se puede escribir: `-11111111`, o `-11_111_111`.

Los números positivos no requieren un signo positivo antepuesto, pero es permitido, si se desea hacer. Las siguientes líneas describen el mismo número: `+11111111` y `11111111`.

### Enteros: números octales y hexadecimales

Normalmente representamos los números con representación decimal, pero Python nos permite utilizar un número en su representación octal (para le representación de los números se utilizan 8 dígitos del 0 al 7).

Si un número entero esta precedido por un código `0O` o `0o` (cero-o), el número será tratado como un valor octal. Esto significa que el número debe contener dígitos en el rango del [0..7] únicamente.

`0o123` es un número octal con un valor (decimal) igual a 83.

La función `print()` realiza la conversión automáticamente. Intenta esto:

```
print(0o123) 
```

También nos permite utilizar números en hexadecimal (para le representación de los números se utilizan 16 dígitos del 0 al F). Dichos números deben ser precedidos por el prefijo `0x` o `0X` (cero-x).

`0x123` es un número hexadecimal con un valor (decimal) igual a 291. La función `print()` puede manejar estos valores también. Intenta esto:

```
print(0x123)
```

## Literales flotantes

Los números flotantes tienen (o pueden tener) una parte fraccionaria después del punto decimal.

Cuando se usan términos como dos y medio o menos cero punto cuatro, pensamos en números que el ordenador considera como números punto-flotante:

```
2.5
-0.4
```

En Python para dividir la parte entera y decimal se utiliza **el punto**. Ejemplos:

* Escribir el numero *3 coma 8*: `3.8`.
* Escribir el número *cero coma cinco*: `0.5`.
* Se puede omitir el cero cuando es el único dígito antes o después del punto decimal:
    * El valor `0.5` se puede escribir como `.5`.
    * El valor `5.0` puede ser escrito como: `5.`

### Enteros frente a Flotantes

El **punto** decimal es esencialmente importante para reconocer números punto-flotantes en Python.

Observa estos dos números:

```
4
4.0
```

Se puede pensar que son idénticos, pero Python los ve de una manera completamente distinta: **4 es un número entero, mientras que 4.0 es un número punto-flotante**. El punto decimal es lo que determina si es flotante.

Por otro lado, no solo el punto hace que un número sea flotante. Se puede utilizar la letra **e** Cuando se desea utilizar números que son muy pequeños o muy grandes, se puede implementar la notación científica.

Por ejemplo, la velocidad de la luz, expresada en metros por segundo. Escrita directamente se vería de la siguiente manera: `300000000`.

Para evitar escribir tantos ceros, los libros de texto emplean la forma abreviada, la cual probablemente hayas visto: 3 x 10<sup>8</sup>. Se lee de la siguiente manera: tres por diez elevado a la octava potencia.

En Python, el mismo número se puede representar con `3E8`. La letra `E` (también se puede utilizar la letra minúscula `e` - proviene de la palabra exponente) la cual significa por diez a la n potencia.

Nota:

* El exponente (el valor después de la `E`) debe ser un valor entero.
* La base (el valor antes de la `E`) puede o no ser un valor entero.

### Codificando Flotantes

Veamos ahora como almacenar números que son muy pequeños (en el sentido de que están muy cerca del cero).

Una constante de física denominada "La Constante de Planck" (denotada como h), de acuerdo con los libros de texto, tiene un valor de: 6.62607 x 10<sup>-34</sup>.

Si se quisiera utilizar en un programa, se debería escribir de la siguiente manera: `6.62607E-34`

El hecho de que se haya escogido una de las posibles formas de codificación de un valor flotante no significa que Python lo presentará de la misma manera.

Python podría en ocasiones elegir una notación diferente.


Por ejemplo, supongamos que se ha elegido utilizar la siguiente notación:

```
0.0000000000000000000001
```

Cuando se corre en Python:

```
print(0.0000000000000000000001)
```

Este es el resultado:

```
1e-22
```

Python siempre elige la **presentación más corta del número**, y esto se debe de tomar en consideración al crear literales.