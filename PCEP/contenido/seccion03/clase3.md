# Literales cadenas de caracteres y booleanos

## Cadenas de caracteres

Las cadenas se emplean cuando se requiere representar texto, no números.

Para representar una cadena de caracteres se utilizan las **comillas dobles o simples**. Este es un ejemplo de una cadena: `"Yo soy una cadena."`.

Supongamos que se desea mostrar un muy sencillo mensaje:

```
Me gusta "Monty Python"
```

Cómo se puede codificar las comillas como parte de la cadena de caracteres. Tenemos dos posibilidades:

1. La primera se basa en el concepto ya conocido del **carácter de escape**, el cual recordarás se utiliza empleando la diagonal invertida. La diagonal invertida puede también escapar las comillas. 

    ```
    print("Me gusta \"Monty Python\"")
    ```

2. La segunda solución sería usar una comilla simple para delimitar la cadena.

    ```
    print('Me gusta "Monty Python"')
    ```

De manera similar podemos codificar una comilla simple dentro de la cadena. También tenemos las mismas dos soluciones:

```
print('I\'m Monty Python.')
```
o

```
print("I'm Monty Python.")
```

Por último, indicar que una una cadena puede estar vacía, puede no contener carácter alguno.

Una cadena vacía sigue siendo una cadena:

```
''
""
```

## Valores booleanos

Además de los anteriores tenemos dos literales del tipo lógico o booleano.

No son tan obvios como los anteriores y se emplean para representar un valor muy abstracto: **la veracidad**.

Cada vez que se le pregunta a Python si un número es más grande que otro, el resultado es la creación de un tipo de dato muy específico: **un valor booleano**.

El nombre proviene de *George Boole (1815-1864)*, el autor de *Las Leyes del Pensamiento*, las cuales definen el *Álgebra Booleana*: una parte del álgebra que hace uso de dos valores: **Verdadero y Falso**, denotados como 1 y 0.

Cuando en Python la ejecución de un código depende de una condición, la respuesta siempre es verdadero o falso, dicho de otra manera los ordenadores solo conocen dos tipos de respuestas:

* Si, esto es verdad.
* No, esto es falso.

Nunca habrá una respuesta como: *No lo sé o probablemente si, pero no estoy seguro*.

Estos dos valores booleanos se representan en Python con los literales booleanos:

```
True
False
```

Reto: ¿Cuál será el resultado del siguiente fragmento de código?

```
print(True > False)
print(True < False)
```

## El valor None

Existe un literal especial más utilizado en Python: el literal `None`. Este literal es llamado un objeto de `NoneType`, y puede ser utilizado para representar la ausencia de un valor. Pronto se hablará más acerca de ello.

## Cuestionario

1. ¿Qué tipos de literales son los siguientes dos ejemplos?

    ```
    "Hola ", "007"
    ```

2. ¿Qué tipos de literales son los siguientes cuatro ejemplos?

    ```
    "1.5", 2.0, 528, False
    ```

3. ¿Cuál es el valor decimal del siguiente número binario?

    ```
    1011
    ```

4. ¿Cuál de las siguientes `print()` invocaciones de función generarán un SyntaxError?

    ```
    print('Greg\'s book.')
    print("'Greg's book.'")
    print('"Greg\'s book."')
    print("Greg\'s book.")
    print('"Greg's book."')
    ```

## Solución cuestionario

1. Pregunta 1:

    Ambos son literales de cadena.

2. Pregunta 2:

    El primero es una cadena, el segundo es un literal numérico (un flotante), el tercero es un literal numérico (un entero) y el cuarto es un literal booleano.

3. Pregunta 3:

    Es 11, porque (2<sup>0</sup>) + (2<sup>1</sup>) + (2<sup>3</sup>) = 11

4. Pregunta 4:

    La línea 5 generará un `SyntaxError`, porque el símbolo `'` en la cadena `Greg's book.` requiere un carácter de escape.