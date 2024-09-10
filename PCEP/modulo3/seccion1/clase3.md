# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 1: Toma de decisiones en Python
## Clase: Condiciones y ejecución condicional

### Condiciones y ejecución condicional

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

