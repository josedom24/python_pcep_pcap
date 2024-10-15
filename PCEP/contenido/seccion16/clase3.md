# Pruebas de ejecución

Aunque hemos visto la posibilidad de gestionar los posibles errores que se pueden provocar en un programa con el manejo de las excepciones, ese mecanismo no nos asegura que nuestro programa este libre de errores.

Además en un lenguaje interpretado, determinados errores sólo se descubren cuando se ejecuta la instrucción que contiene el error. Por ello sería necesario probar todas las posibilidades de valores de entrada para asegurar la ejecución de todas las instrucciones bajo todas las posibilidades y determinar si alguna produce algún error.

Realmente probar nuestros programas nos permite encontrar errores, pero la mayoría de las veces es complicado probar todas las posibilidades de ejecución de un programa. En muchas ocasiones, hay personas dedicadas a realizar las pruebas, son los llamados tester, sin embargo no está de más que el propio programador aprenda distintas técnicas para probar sus programas.

## Ejemplo de prueba

Si hemos desarrollado el siguiente programa:

```
temperature = float(input('Ingresa la temperatura actual:'))

if temperature > 0:
    print("Por encima de cero")
elif temperature < 0:
    print("Por debajo de cero")
else:
    print("Cero")
```

Nos damos cuenta que hay tres alternativas de ejecución según el valor de la variable `temperature`. 
Este ejemplo es sencillo y deberíamos probar el programa con tres tipos de valores:

* Cuando la variable `temperature` es positiva.
* Cuando la variable `temperature` es negativa.
* Cuando la variable `temperature` es 0.

Veamos otro ejemplo, ahora hemos creado un programa similar al anterior:

```
temperature = float(input('Ingresa la temperatura actual:'))

if temperature > 0:
    print("Por encima de cero")
elif temperature < 0:
    prin("Por debajo de cero")
else:
    print("Cero")
```

Hemos introducido un error sintáctico. Si el programa fuera más grande quizás sería complicado verlo a simple vista.

Como hemos dicho anteriormente, el programa deberíamos probarlos en las tres circunstancia: variable positiva, variable negativa y variable igual a 0.

En este caso si la variable es positiva o igual a 0, el programa funciona sin problemas, pero cuando introducimos un valor negativo, el programa nos da un error de tipo `NameError` al no reconocer la instrucción *prin*.

Al ser Python un lenguaje interpretado, donde el código fuente se analiza y ejecuta al mismo tiempo. Los errores no suelen aparecer hasta que no se analiza la instrucción que se va a ejecutar.

## Depuración de programas

Otra técnica para intentar evitar que un programa tenga errores es la **depuración**. 

Un **depurador** es un software especializado que puede controlar cómo se ejecuta tu programa. Con el depurador, puedes ejecutar tu código línea por línea, inspeccionar todos los estados de las variables y cambiar sus valores en cualquier momento sin modificar el código fuente, detener la ejecución del programa cuando se cumplen o no ciertas condiciones, y hacer muchas otras tareas útiles.

Cualquier IDE que utilizamos tiene un depurador incorporado. IDLE también tiene un depurador que podemos activar con la opción *Debug*. En el siguiente apartado veremos un ejemplo de depuración con IDLE.

## Depuración por impresión

Esta técnica de depuración es más sencilla y menos potente que el uso de un depurador, pero en ciertas circunstancias puede ser muy útil.

La **depuración por impresión** consiste en ir insertando distintas instrucciones `print()` entre el código para visualizar el valor de va tomando cierta variable. Además de imprimir el valor de las variables, podemos insertar impresiones de mensajes significativos para asegurarnos que se está ejecutando esa parte del código.

Evidentemente, después de hacer esta depuración y arreglar el error estas instrucciones `print()` se suelen borrar.

Veamos un ejemplo, donde queremos imprimir la suma de los números guardados en una lista:

```
lista = [3, 5, 7, 8]
suma=0
for num in lista:
    print(num) # Quiero saber que valor va tomando la variable de control  bucle
    suma += num
    print(suma) # Quiero saber que valor se va acumulando en la variable suma
print(suma)
```

## Pruebas unitarias

Por último, una técnica cada vez más usada para probar nuestros programas e intentar encontrar los posibles errores son las **pruebas unitarias**.

En este caso, cuando escribimos u programa, o una función, también programamos una prueba con un lote de datos significativo que nos permite probar el código de una forma más eficiente. Es decir, escribimos un programa que prueba una función o un programa.

Además es posible que esos programas de prueba se ejecuten de forma automática cada vez que se cambia el código, es lo que llamamos **integración continúa**, asegurando que cualquier cambio del código sigue funcionando de manera adecuada o ha introducido algún error.

Python proporciona un módulo dedicado llamado `unittest` que nos permite la creación de pruebas unitarias.
