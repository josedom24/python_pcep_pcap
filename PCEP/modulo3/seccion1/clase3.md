# Condiciones y ejecución condicional

## Condiciones y ejecución condicional

Ya sabes como hacer preguntas a Python, pero aún no sabes como hacer un uso razonable de las respuestas. Se debe tener un mecanismo que le permita hacer algo si se cumple una condición, y no hacerlo si no se cumple.

Es como en la vida real: haces ciertas cosas o no cuando se cumple una condición específica, por ejemplo, sales a caminar si el clima es bueno, o te quedas en casa si está húmedo y frío.

Para tomar tales decisiones, Python ofrece una instrucción especial. Debido a su naturaleza y su aplicación, se denomina **instrucción condicional (o sentencia condicional)**.

Existen varias variantes de la misma. Comenzaremos con la más simple, aumentando la dificultad lentamente.

La primera forma de una sentencia condicional, que puede ver a continuación, está escrita de manera muy informal pero figurada:
```
if true_or_not:
    do_this_if_true
```

Esta sentencia condicional consta de los siguientes elementos, estrictamente necesarios en este orden:

* La palabra clave reservada `if`.
* Uno o más espacios en blanco.
* Una expresión condicional (una pregunta o una respuesta) cuyo valor se interpretar únicamente en términos de `True`  y `False` .
* Unos dos puntos seguido de una nueva línea.
* Una instrucción con **sangría** o un conjunto de instrucciones (se requiere absolutamente al menos una instrucción); la sangría se puede lograr de dos maneras: 
    * insertando un número particular de espacios (la recomendación es usar cuatro espacios de sangría), 
    * o usando el tabulador; 
    * nota: si hay mas de una instrucción en la parte con sangría, la sangría debe ser la misma en todas las líneas; aunque puede parecer lo mismo si se mezclan tabuladores con espacios, es importante que todas las sangrías sean exactamente iguales Python 3 no permite mezclar espacios y tabuladores para la sangría.

¿Cómo funciona esta sentencia?

* Si la expresión *true_or_not* representa la verdad (es decir, su valor es `True`), las sentencias con sangría se ejecutarán.
* Si la expresión *true_or_not* no representa la verdad (es decir, su valor es `False``), las sentencias con sangría se omitirán , y la siguiente instrucción ejecutada será la siguiente al nivel de la sangría original.

Ejemplo, si en la vida real podemos expresar la siguiente frase:

*Si el clima es bueno, saldremos a caminar después, almorzaremos*.

Como puedes ver, almorzar no es una actividad condicional y no depende del clima.

Podríamos indicarlo en un programa asumiendo que tenemos las funciones sin parámetros `go_for_a_walk()` y `have_lunch()`, de la siguiente manera:

```
if the_weather_is_good:
    go_for_a_walk()
have_lunch()
```


## Ejecución condicional: la sentencia if

Empecemos con ejemplo: si un determinado desarrollador de Python sin dormir se queda dormido cuando cuenta 120 ovejas, y el procedimiento de inducción del sueño se puede implementar como una función especial llamada `sleep_and_dream()`, el código toma la siguiente forma:

```
if sheep_counter >= 120: # #evalúa una expresión condicional
    sleep_and_dream() #se ejecuta si la expresión condicional es True
```

El programa anterior lo podemos leer: si `sheep_counter` es mayor o igual que 120, entonces duerme y sueña (es decir, ejecuta la función `sleep_and_dream`).

Hemos dicho que las sentencias condicionales deben tener sangría. Esto crea una estructura muy legible, demostrando claramente todas las rutas de ejecución posibles en el código.

Analiza el siguiente código:

```
if sheep_counter >= 120:
    make_a_bed()
    take_a_shower()
    sleep_and_dream()
feed_the_sheepdogs()
```

Como puedes ver, *hacer la cama*, *ducharse* y *dormir y soñar* se ejecutan condicionalmente, cuando `sheep_counter` alcanza el límite deseado.

*Alimentar a los perros*, sin embargo, siempre se hace (es decir, la función `feed_the_sheepdogs()` no tiene sangría y no pertenece al bloque if, lo que significa que siempre se ejecuta).

A continuación vamos a discutir otra variante de la sentencia condicional, que también permite realizar una acción adicional cuando no se cumple la condición.

## Ejecución condicional: la sentencia if-else

Veamos un ejemplo:

* Comenzamos con una frase simple que decía: **Si el clima es bueno, saldremos a caminar**.
* No hemos dicho nada sobre lo que sucederá si el clima es malo. Solo sabemos que no saldremos a caminar, pero no sabemos que podríamos hacer. Es posible que también queramos planificar algo en caso de mal tiempo.
* Podemos decir, por ejemplo: **Si el clima es bueno, saldremos a caminar, de lo contrario, iremos al cine.**
* Ahora sabemos lo que haremos si se cumplen las condiciones, y sabemos lo que haremos si no todo sale como queremos. En otras palabras, tenemos un "Plan B".

Python nos permite expresar dichos planes alternativos. Esto se hace con una segunda forma, ligeramente mas compleja, de la sentencia condicional, la sentencia `if-else`:

```
if true_or_false_condition:
    perform_if_condition_true
else:
    perform_if_condition_false
```

Por lo tanto, hay una nueva palabra clave reservada: **else**.

La parte del código que comienza con `else` dice que hacer si no se cumple la condición especificada por el `if` (observa los dos puntos después de la palabra).

La ejecución de `if-else` es la siguiente:

* Si la condición se evalúa como `True`, la instrucción `perform_if_condition_true` se ejecuta, y la sentencia condicional llega a su fin.
* Si la condición se evalúa como `False`, la instrucción `perform_if_condition_false` se ejecuta, y la sentencia condicional llega a su fin.


## La sentencia if-else: más sobre ejecución condicional

Al utilizar esta forma de sentencia condicional, podemos describir nuestros planes de la siguiente manera:

```
if the_weather_is_good:
    go_for_a_walk()
else:
    go_to_a_theater()
have_lunch()
```

Si el clima es bueno, saldremos a caminar. De lo contrario, iremos al cine. No importa si el clima es bueno o malo, almorzaremos después (después de la caminata o después de ir al cine).

Todo lo que hemos dicho sobre la sangría funciona de la misma manera dentro de la rama else :

```
if the_weather_is_good:
    go_for_a_walk()
    have_fun()
else:
    go_to_a_theater()
    enjoy_the_movie()
have_lunch()
```

## Sentencias if-else anidadas

Ahora, analicemos dos casos especiales de la sentencia condicional.

Primero, considera el caso donde la instrucción colocada después del if es otro if.

El ejemplo podría ser el siguiente: 

Si hay buen clima, saldremos a caminar. Si encontramos un buen restaurante, almorzaremos allí. De lo contrario, vamos a comer un sandwich. Si hay mal clima, iremos al cine. Si no hay boletos, iremos de compras al centro comercial más cercano.

Escribamos lo mismo en Python. Considera cuidadosamente el código siguiente:

```
if the_weather_is_good:
    go_for_a_walk()
    if nice_restaurant_is_found:
        have_lunch()
    else:
        eat_a_sandwich()
else:
    if tickets_are_available:
        go_to_the_theater()
    else:
        go_shopping()
```

Aquí hay dos puntos importantes:

* Este uso de la sentencia if se conoce como **anidamiento**; recuerda que cada `else` se refiere al `if` que se encuentra en el mismo nivel de sangría; se necesita saber esto para determinar cómo se relacionan los `if` y los `else`.
* Considera como la sangría mejora la legibilidad y hace que el código sea más fácil de entender y rastrear.

## La sentencia elif

El segundo caso especial presenta otra nueva palabra clave de Python: **elif**. Como probablemente sospechas, es una forma más corta de else-if.

`elif` se usa para verificar más de una condición, y para detener cuando se encuentra la primera sentencia verdadera.

Nuestro siguiente ejemplo se parece a la anidación, pero las similitudes son muy leves. Nuevamente, cambiaremos nuestros planes y los expresaremos de la siguiente manera: si hay buen clima, saldremos a caminar, de lo contrario, si obtenemos entradas, iremos al cine, de lo contrario, si hay mesas libres en el restaurante, vamos a almorzar; si todo falla, regresaremos a casa y jugaremos ajedrez.

¿Has notado cuantas veces hemos usado la palabra de lo contrario? Esta es la etapa en la que la palabra clave reservada `elif` desempeña su función.

Escribamos el mismo escenario empleando Python:

```
if the_weather_is_good:
    go_for_a_walk()
elif tickets_are_available:
    go_to_the_theater()
elif table_is_available:
    go_for_lunch()
else:
    play_chess_at_home()
```

La forma de ensamblar las siguientes sentencias `if-elif-else` a veces se denomina **cascada**.

Observa de nuevo como la sangría mejora la legibilidad del código.

Se debe prestar atención adicional a este caso:

* No debes usar `else` sin un `if` precedente.
* `else` siempre es la última rama de la cascada, independientemente de si has usado `elif` o no.
* `else` es una parte opcional de la cascada, y puede omitirse.
* Si hay una rama `else` en la cascada, solo se ejecuta una de todas las ramas.
* Si no hay una rama `else`, es posible que no se ejecute ninguna de las opciones disponibles.



