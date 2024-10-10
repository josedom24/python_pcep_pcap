# Operadores lógicos o de comparación

## Preguntas y respuestas

La mayoría de los programas que hacemos **hacen preguntas**. El programa se puede comportar de manera distinta según los datos de entrada recibidos. 

Afortunadamente, los ordenadores solo conocen dos tipos de respuestas:

* **Si, es cierto.**
* **No, es falso.**

Nunca obtendrás una respuesta como: *Déjame pensar...*,* no lo sé*, o *probablemente sí, pero no lo sé con seguridad*.

Para hacer preguntas, Python utiliza un conjunto de operadores, que llamamos **operadores lógicos o de comparación**.

## Comparación: operador de igualdad

Pregunta: ¿Son dos valores iguales?

Para hacer esta pregunta, se utiliza el operador `==`. Hay que distinguir lo siguiente:

* `=` es un **operador de asignación**, por ejemplo, `a = b` asigna a la variable `a` el valor de `b`.
* `==` es un **operador lógico o de comparación**: ¿Son estos valores iguales? así que `a == b` compara `a` y `b`.

Es un operador binario que necesita dos argumentos y verifica si son iguales.Si son iguales, el resultado de la comparación es `True`. Si no son iguales, el resultado de la comparación es `False`.

Ejemplo: ¿Cuál es el resultado de esta operación?

```
var == 0
```

* Ten en cuenta que no podemos encontrar la respuesta si no sabemos qué valor está almacenado actualmente en la variable `var`.
* Si la variable se ha cambiado muchas veces durante la ejecución del programa, o si se ingresa su valor inicial desde la consola, Python solo puede responder a esta pregunta en el **tiempo de ejecución del programa**.

Otro ejemplo, imagina a un programador que sufre de insomnio, y tiene que contar las ovejas negras y blancas, debe comprobar cuando hay exactamente el doble de ovejas negras que de las blancas.

La pregunta será la siguiente:

```
black_sheep == 2 * white_sheep
```

Debido a la baja prioridad del operador ==, la pregunta será tratada como la siguiente:

```
black_sheep == (2 * white_sheep)
```

Ejercicios de comparación:

1. ¿Cuál es el resultado de la siguiente comparación?

    `2 == 2`

    * Solución: `True`, por supuesto, 2 es igual a 2. 

2. ¿Cuál es el resultado de la siguiente comparación?

    `2 == 2.`

    * Solución: Esta pregunta no es tan fácil como la primera. Por suerte, Python es capaz de convertir el valor entero en su equivalente real, y en consecuencia, la respuesta es `True`.

3. ¿Cuál es el resultado de la siguiente comparación?

    `1 == 2`

    * Solución: Esto debería ser fácil. La respuesta es `False`.

4. ¿Puedes adivinar la salida del código a continuación?

    ```
    var = 0   # asignando 0 a var
    print(var == 0)
    
    var = 1  # asignando 1 a var
    print(var == 0)
    ```

    * Solución: La salida será: `True False`.
    
## Comparación: operador de desigualdad

El operador `!=` (no es igual a) también compara los valores de dos operandos. Aquí está la diferencia: si son iguales, el resultado de la comparación es `False`. Si no son iguales, el resultado de la comparación es `True`.

Ahora echa un vistazo a la comparación de desigualdad a continuación: ¿Puedes adivinar el resultado de esta operación?

    ```
    var = 0 # asignando 0 a var
    print(var != 0)

    var = 1 # asignando 1 a var
    print(var != 0)
    ```

Ejecuta el código y comprueba si tenías razón.

## Comparación: mayor que y mayor que o igual

También se puede hacer una pregunta de comparación usando el operador `>` (mayor que) o el operador `>=` (mayor o igual que). Ambos operadores **son binarios, asociativos a la izquierda y su prioridad es mayor que la mostrada por `==` y `!=`**.

* Si deseas saber si hay más ovejas negras que blancas, puedes escribirlo de la siguiente manera: `black_sheep > white_sheep`.
* Si queremos saber si tenemos que usar un gorro o no, nos hacemos la siguiente pregunta: `centigrade_outside ≥ 0.0`.

`True` lo confirma; `False` lo niega.

## Comparación: menor que y menor que o igual

De manera similar a lo visto anteriormente, podemos usar el operador `<`(menor que) y el operador `<=` (menor o igual que).

Observa este ejemplo simple:

```
current_velocity_mph < 85  # Menor que
current_velocity_mph ≤ 85  # Menor o igual que
```

## Haciendo uso de las respuestas

¿Qué puedes hacer con la respuesta (es decir, el resultado de una operación de comparación) que se obtiene del ordenador?

1. Puedes memorizarlo (almacenarlo en una variable) y utilizarlo más tarde. ¿Cómo haces eso? Bueno, utilizarías una variable arbitraria como esta:

    ```
    answer = number_of_lions >= number_of_lionesses
    ```

    La Variables `answer` es de **tipo lógica o booleana**, y contiene dos posible valores: o `True` o `False`.
    ```
    type(answer)
    ```

2. Es más conveniente y mucho más común utilizar la respuesta que obtengas para tomar una decisión sobre el futuro del programa. Para ello, necesitamos una instrucción especial que estudiaremos a continuación.


Vamos actualizar la **tabla de prioridades** de operadores:

1. `+`,`-` (unarios)
2. `**`
3. `*`,`/`,`//`,`%`
4. `+`,`-` (binarios)
5. `<`, `<=`, `>`, `>=` 	
6. `==`, `!=`

## Resumen

La siguiente tabla ilustra cómo funcionan los operadores de comparación, asumiendo que `x=0`, `y=1` y `z=0`:

|Operador |	Descripción |Ejemplo|
|----------|----------|----------|
|== 	|Devuelve True si los valores son iguales, y False de lo contrario.| x == y  # False <br> x == z  # True|
|!= 	|Devuelve True si los valores no son iguales, y False de lo contrario.|x != y  # True <br> x != z  # False|
|> 	    |Devuelve True si el primer valor es mayor que el valor del segundo, y False de lo contrario.|x > y  # False <br> y > z  # True|
|< 	    | Devuelve True si el primer valor es menor que el valor del segundo, y False de lo contrario.| x < y  # True <br> y < z  # False |
|≥ 	    | Devuelve True si el primer valor es mayor o igual al valor del segundo, y False de lo contrario.| x >= y  # False <br> x >= z  # True <br> y >= z  # True|
|≤ 	    | Devuelve True si el primer valor es menor o igual al valor del segundo, y False de lo contrario. | x <= y  # True <br> x <= z  # True <br> y <= z  # False |