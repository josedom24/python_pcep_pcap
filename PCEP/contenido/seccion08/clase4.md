# LABORATORIO - Fundamentos del bucle for: contador

## Tiempo Estimado

5 minutos

## Nivel de Dificultad

Muy fácil

## Objetivos

Familiarizar al estudiante con:

* Utilizar el bucle `for`.
* Reflejar situaciones de la vida real en un programa de ordenador.

## Escenario

Mississippi es el nombre de uno de los estados y ríos en los Estados Unidos. 

La palabra Mississippi también se usa para un propósito ligeramente diferente: para contar *mississippimente*, es decir se usa para contar segundos.

La idea detrás de esto es que agregar la palabra Mississippi a un número al contar los segundos en voz alta hace que suene más cercano al reloj, y por lo tanto "uno Mississippi, dos Mississippi, tres Mississippi" tomará aproximadamente unos tres segundos reales de tiempo.

Tu tarea es muy simple aquí: escribe un programa que use un bucle `for` para "contar de forma mississippi" hasta cinco. Habiendo contado hasta cinco, el programa debería imprimir en la pantalla el mensaje final `"¡Listos o no, ahí voy!"`

Utiliza la siguiente plantilla para comenzar el programa:

```
import time

    # Escribe un bucle for que cuente hasta cinco.
    # Cuerpo del bucle: imprime el número de iteración del bucle y la palabra "Mississippi".
    # Cuerpo del bucle - usar: time.sleep (1)

# Escribe una función de impresión con el mensaje final.
```

En el código anterior hay dos elementos que todavía no hemos explicado: la instrucción `import time` y el método `sleep()`. 

Hemos importado el módulo `time` y hemos utilizado el método `sleep()` para suspender la ejecución de cada función posterior de `print()` dentro del bucle `for` durante un segundo, de modo que el mensaje enviado a la consola se parezca a un conteo real. No te preocupes, pronto aprenderás más sobre módulos y métodos.

## Salida esperada

```
1 Mississippi
2 Mississippi
3 Mississippi
4 Mississippi
5 Mississippi
¡Listos o no, ahí voy!
```

