# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 1: El Programa "¡Hola, Mundo!"
## Clase: Instrucciones

### Un programa está formado por instrucciones

Ya has visto un programa de ordenador que contiene una invocación de función. La invocación de una función es uno de los muchos tipos posibles de **instrucciones** de Python.

Python requiere que no haya más de una instrucción por línea. Una línea puede estar vacía (por ejemplo, puede no contener ninguna instrucción) pero no debe contener dos, tres o más instrucciones. Esto está estrictamente prohibido.

> Nota: Python hace una excepción a esta regla: permite que una instrucción se extienda por más de una línea (lo que puede ser útil cuando el código contiene construcciones complejas).

Vamos a escribir un segundo programa con dos instrucciones:

```
print("La Araña Witsi Witsi subió a su telaraña.")
print("Vino la lluvia y se la llevó.")
```

De la ejecución del programa, podemos hacer algunas observaciones:

* El programa invoca la función `print()` dos veces (de forma secuencial, primero ejecuta la primera instrucción y a continuación la segunda), como puedes ver hay dos líneas separadas en la consola: esto significa que `print()` comienza su salida desde una nueva línea cada vez que comienza su ejecución. Puedes cambiar este comportamiento, pero también puedes usarlo a tu favor.
* Cada invocación de `print()` contiene una cadena diferente, como su argumento y el contenido de la consola lo reflejan, esto significa que las instrucciones en el código se ejecutan en el mismo orden en que se colocaron en el archivo fuente; no se ejecuta la siguiente instrucción hasta que se complete la anterior (hay algunas excepciones a esta regla, pero puedes ignorarlas por ahora).


Hemos cambiado un poco el ejemplo - hemos agregado una invocación vacía de la función `print()`. La llamamos vacía porque no hemos entregado ningún argumento a la función.

```
print("La Araña Witsi Witsi subió a su telaraña.")
print()
print("Vino la lluvia y se la llevó.")
```
Ejecuta el código. ¿Qué sucede?
Como puedes ver, la invocación vacía de `print()` no está tan vacía como podrías haber esperado - genera una línea vacía o (esta interpretación también es correcta) genera una nueva línea.

### Caracteres de escape y nueva línea en Python

Hemos modificado el código de nuevo. Hay dos cambios muy sutiles: hemos insertado un par extraño de caracteres dentro del texto. Se ven así: `\n`.

```
print("La Araña Witsi Witsi\n subió a su telaraña.\n")
print()
print("Vino la lluvia\n y se la llevó.")
```

Para Pythón `\n` es un sólo carácter. La barra invertida (`\`) tiene un significado muy especial cuando se usa dentro de cadenas, se llama **carácter de escape**, es decir, la serie de caracteres en la cadena se escapa por un momento para introducir una inclusión especial. Es una especie de anuncio de que el siguiente carácter después de la barra invertida también tiene un significado diferente.

La letra `n` colocada después de la barra invertida proviene de la palabra *newline*. Tanto la barra invertida como la `n` forman un símbolo especial llamado *un carácter de nueva línea*, que insta a la consola a iniciar una nueva línea de salida.

Si ejecutas el código, la salida se debería mostrar así:

```
La Araña Witsi Witsi
subió a su telaraña.
 
Vino la lluvia
y se la llevó. 
```
Esta convención tiene dos consecuencias importantes:

1. Si deseas colocar solo una barra invertida dentro de una cadena, no olvides su naturaleza de escape, tienes que duplicarla:
    ```
    print("\\")
    ```
2. No todos los pares de escape (la barra invertida junto con otro carácter) significan algo.

