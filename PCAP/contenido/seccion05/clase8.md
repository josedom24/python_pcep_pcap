# Comparación de cadenas

En Python, las cadenas de texto pueden compararse utilizando los mismos operadores que se emplean con los números, tales como `==`, `!=`, `>`, `>=`, `<` y `<=`. Sin embargo, a pesar de que estos operadores son útiles, los resultados de las comparaciones de cadenas pueden ser inesperados si no se comprenden algunas características básicas del lenguaje.

## Operadores para comparar cadenas

* **Igualdad (`==`)**: Dos cadenas son iguales si contienen exactamente los mismos caracteres en el mismo orden.
* **Desigualdad (`!=`)**: Dos cadenas no son iguales si tienen diferentes caracteres o están en un orden distinto.
  
    Ejemplos:
    ```
    'alpha' == 'alpha'  # True
    'alpha' != 'Alpha'  # True
    ```

    En este caso, las dos cadenas son diferentes porque Python distingue entre mayúsculas y minúsculas, lo que hace que `'alpha'` y `'Alpha'` no sean iguales.

## Comparaciones basadas en puntos de código

Python compara las cadenas carácter por carácter, basándose en el valor de sus puntos de código (ASCII o Unicode). Esto significa que no tiene en cuenta aspectos lingüísticos o contextuales, solo compara los números asociados a cada carácter.

1. **Comparación entre cadenas de diferente longitud**: Si dos cadenas tienen caracteres idénticos, pero una es más larga, Python considera mayor a la más larga.

    Ejemplo:
    ```
    'alpha' < 'alphabet'  # True
    ```

    Aquí, Python determina que `'alpha'` es menor porque la cadena corta coincide en sus primeros caracteres con la cadena más larga, pero la cadena larga tiene más caracteres.

2. **Diferencia entre mayúsculas y minúsculas**: En Python, las letras mayúsculas tienen un valor de punto de código menor que las minúsculas. Por lo tanto, las letras mayúsculas se consideran "menores" al compararse con las minúsculas.

    Ejemplo:
    ```
    'beta' > 'Beta'  # True
    ```

    Python determina que `'beta'` es mayor que `'Beta'` porque la letra minúscula `'b'` tiene un valor de punto de código mayor que `'B'`.

## Comparación de cadenas que contienen dígitos

En Python, incluso si una cadena contiene solo dígitos, **sigue siendo tratada como una cadena y no como un número**. Esto significa que las comparaciones entre cadenas de dígitos no toman en cuenta su valor numérico, sino su valor como texto. Así, los resultados pueden ser inesperados si no se entiende esta distinción.

Al comparar cadenas que contienen dígitos, se comparan carácter por carácter, siguiendo el valor de los puntos de código, no los valores numéricos reales.

Observemos los siguientes ejemplos:

```
'10' == '010'  # `False`
'10' > '010'   # True
'10' > '8'     # `False`
'20' < '8'     # True
'20' < '80'    # True
```

* `'10' == '010'` es **falso** porque, aunque ambas cadenas parecen representar el mismo número, los caracteres no coinciden.
* `'10' > '010'` es **verdadero** porque Python compara carácter por carácter, y el primer carácter de `'10'` es mayor que el primer carácter de `'010'`.
* `'10' > '8'` es **falso**, ya que en términos de cadenas, el valor `'8'` tiene un punto de código mayor que el carácter `'1'` de `'10'`.
* `'20' < '8'` y `'20' < '80'` producen **resultados sorprendentes** porque no se evalúan como números, sino como texto, comparando caracteres individuales.

Comparar una cadena directamente con un número **genera errores** en Python, ya que son tipos de datos incompatibles. Las únicas comparaciones seguras entre cadenas y números son las de igualdad (`==`) o desigualdad (`!=`). Usar otros operadores, como `<` o `>`, resulta en una excepción **TypeError**.

Ejemplos:

```
'10' == 10      # `False`
'10' != 10      # True
'10' == 1       # `False`
'10' != 1       # True
'10' > 10       # TypeError
```

* Las comparaciones de **igualdad** (`==`) y **desigualdad** (`!=`) entre cadenas y números devuelven resultados previsibles (`False` y `True`, respectivamente): como son de tipos de datos diferentes (cadena vs. número), la comparación da como resultado `False`.
* Cualquier otro operador de comparación, como `>` o `<`, genera una **excepción `TypeError`**, ya que Python no puede comparar directamente cadenas y números.


