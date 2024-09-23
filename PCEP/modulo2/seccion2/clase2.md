# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 2: Literales de Python 
## Clase: Enteros

## Literales enteros

Los ordenadores guardan y operan con los números utilizando el sistema binario. Internamente todos los números se representan, se guardan y se operan utilizando 0 y 1.

No exploraremos las complejidades de los sistemas numéricos posicionales, pero se puede afirmar que todos los números manejados por los ordenadores son de dos tipos:

* **Enteros**, es decir, aquellos que no tienen una parte fraccionaria.
* Y números **punto-flotantes** (o simplemente **flotantes** o **reales**), los cuales contienen (o son capaces de contener) una parte fraccionaría.

Esta definición no es tan precisa, pero es suficiente por ahora. La distinción es muy importante, y la frontera entre estos dos tipos de números es muy estricta. Ambos tipos difieren significativamente en como son almacenados internamente en el ordenador y en el rango de valores que aceptan.

La característica del valor numérico que determina el tipo, rango y aplicación se denomina el **tipo**.

Si se codifica un literal y se coloca dentro del código de Python, la forma del literal determina la representación (tipo) que Python utilizará para almacenarlo en la memoria.

Por ahora, dejemos los números flotantes a un lado (regresaremos a ellos pronto) y analicemos como es que Python reconoce un número entero.

Python entiende que un número es entero como un conjunto de dígitos sin ningún otro signo diferente a un número. Si queremos representar el número *once millones ciento once mil ciento once*, para Python la forma correcta sería `11111111`. Nosotros podríamos representarlos cómo: `11,111,111`, o así: `11.111.111`, incluso de esta manera: `11 111 111`, pero todas estas formas serían erróneas para Python.

Es claro que la separación hace que sea más fácil de leer, especialmente cuando el número tiene demasiados dígitos. Sin embargo, Python no acepta estas cosas. Está prohibido. ¿Qué es lo que Python permite? El uso de guion bajo en los literales numéricos.

Por lo tanto, el número se puede escribir ya sea así: `11111111`, o como sigue: `11_111_111`. Está última forma se puede hacer desde la versión 2.6 de Python para mejorar la legibilidad.

¿Cómo se codifican los números negativos en Python? Como normalmente se hace, agregando un signo de menos. Se puede escribir: `-11111111`, o `-11_111_111`.

Los números positivos no requieren un signo positivo antepuesto, pero es permitido, si se desea hacer. Las siguientes líneas describen el mismo número: `+11111111` y `11111111`.

## Enteros: números octales y hexadecimales

Existen dos convenciones adicionales en Python que no son conocidas en el mundo de las matemáticas. El primero nos permite utilizar un número en su representación octal (para le representación de los números se utilizan 8 dígitos del 0 al 7).

Si un número entero esta precedido por un código `0O` o `0o` (cero-o), el número será tratado como un valor octal. Esto significa que el número debe contener dígitos en el rango del [0..7] únicamente.

`0o123` es un número octal con un valor (decimal) igual a 83.

La función `print()` realiza la conversión automáticamente. Intenta esto:

```
print(0o123) 
```

La segunda convención nos permite utilizar números en hexadecimal (para le representación de los números se utilizan 16 dígitos del 0 al F). Dichos números deben ser precedidos por el prefijo `0x` o `0X` (cero-x).

`0x123` es un número hexadecimal con un valor (decimal) igual a 291. La función `print()` puede manejar estos valores también. Intenta esto:

```
print(0x123)
```