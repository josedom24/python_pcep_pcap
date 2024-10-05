# Test intermedio

El siguiente test se basa en lo que acabas de aprender. Hay doce preguntas en total y debes obtener al menos un 70 % para aprobar.

1. La definición de una función comienza con la palabra reservada:

    * `def`
    * `fun`
    * `function`

2. La definición de una función:

    * Puede ser colocada en cualquier lugar del código después de la primera invocación
    * Debe ser colocada antes de la primera invocación
    * No debe ser colocada en el código

3. El parámetros de una función es una variable que puede ser accedida:

    * Solo después de la definición de la función
    * En cualquier lugar del código
    * Solo dentro de la función

4. La forma de pasar argumentos en la cual el orden de los argumentos determinar el valor inicial de los parámetros se denomina:

    * Ordenada
    * Posicional
    * Secuencial

5. ¿Cuál de los siguientes argumentos son verdaderos? (Seleccione dos respuestas):

    * [ ] La palabra clave `return` fuerza a la función a reiniciar su ejecución
    * [ ] La palabra clave `return` fuerza a la función a terminar su ejecución
    * [ ] La palabra clave `return` puede ocasionar que la función devuelva un valor

6. La palabra reservada `None` designa:

    * Un valor `None`
    * Una función que no retorna un valor
    * Una instrucción vacía

7. Una variable definida fuera de una función: 

    * Puede ser accedida libremente desde dentro de la función
    * Puede ser leída pero no sobrescrita (se requiere algo más para poder realizar esto)
    * No puede ser accedida desde dentro de una función

8. Si una lista es pasada como argumento a una función, el eliminar cualquiera de sus elementos dentro de la función empleado la instrucción `del`:

    * Afectará al argumento
    * No afectará al argumento
    * Ocasionará un error de ejecución

9. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    def fun(in=2, out=3):
        return in * out
    
    print(fun(3))
    ```

    * 6
    * El código es erróneo (sintaxis inválida)
    * 9

10. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    tup = (1,) + (1,)
    tup = tup + tup
    print(len(tup))
    ```

    * 4
    * 2
    * El código es erróneo (sintaxis inválida)

11. ¿Cuál es la salida del siguiente fragmento de código si el usuario ingresa `kangaroo`y 0 respectivamente?

    ```
    try:
        first_prompt = input("Ingresa el primer valor: ")
        a = len(first_prompt)
        second_prompt = input("Ingresa el segundo valor: ")
        b = len(second_prompt) * 2
        print (a/b)
    except ZeroDivisionError:
        print("No dividas por cero")
    except ValueError:
        print("Valor incorrecto")
    except:
        print("Error. Error. Error")
    ```

    * 4.0
    * No dividas por cero
    * Valor incorrecto
    * Error. Error. Error

12. ¿Cuál es el comportamiento esperado del siguiente programa si el usuario ingresa 0?

    ```
    value = input("Ingresa un valor: ")
    print(10/value)
    ```

    * El programa genera la excepción `ValueError`
    * El programa genera la excepción `ZeroDivisionError`
    * El programa dará como salida `0` en la consola
    * El programa genera la excepción `TypeError`