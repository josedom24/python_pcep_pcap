# Resumen y cuestionario

## Resumen

1. Los **literales** son notaciones para representar valores fijos en el código. Python tiene varios tipos de literales, es decir, un literal puede ser un número por ejemplo, `123`, o una cadena, por ejemplo, `"Yo soy un literal."`.

2. El **sistema binario** es un sistema numérico que emplea 2 como su base. Por lo tanto, un número binario está compuesto por 0s y 1s únicamente, por ejemplo, `1010` es 10 en decimal.
Los sistemas de numeración Octales y Hexadecimales son similares pues emplean 8 y 16 como sus bases respectivamente. El sistema hexadecimal utiliza los números decimales más seis letras adicionales.

3. Los **enteros** (o simplemente **int**) son uno de los tipos numéricos que soporta Python. Son números que no tienen una parte fraccionaria, por ejemplo, `256`, o `-1` (enteros negativos).

4. Los números **punto-flotante** (o simplemente **flotantes**) son otro tipo numérico que soporta Python. Son números que contienen (o son capaces de contener) una parte fraccionaria, por ejemplo, `1.27`.

5. Para codificar un apóstrofe o una comilla dentro de una cadena se puede utilizar el carácter de escape, por ejemplo, `'I\'m happy.'`, o abrir y cerrar la cadena utilizando un conjunto de símbolos distintos al símbolo que se desea codificar, por ejemplo, `"I'm happy."` para codificar un apóstrofe, y `'El dijo "Python", no "typhoon"'` para codificar comillas.

6. Los valores booleanos son dos objetos constantes `True` y `False` empleados para representar valores de verdad (en contextos numéricos 1 es `True`, mientras que 0 es `False`).

7. Extra. Existe un literal especial más utilizado en Python: el literal `None`. Este literal es llamado un objeto de `NoneType`, y puede ser utilizado para representar la ausencia de un valor. Pronto se hablará más acerca de ello.

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

## Solución cuestionario

1. Pregunta 1:

Ambos son literales de cadena.

2. Pregunta 2:

El primero es una cadena, el segundo es un literal numérico (un flotante), el tercero es un literal numérico (un entero) y el cuarto es un literal booleano.

3. Pregunta 3:

E 11, porque (2<sup>0</sup>) + (2<sup>1</sup>) + (2<sup>3</sup>) = 11