# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 3: Operadores, herramientas de manipulación de datos 
## Clase: Operadores básicos

### Python como una calculadora

Ahora, se va a mostrar un nuevo lado de la función `print()`. Ya se sabe que la función es capaz de mostrar los valores de los literales que le son pasados por los argumentos.

De hecho, puede hacer algo más. Observa el siguiente fragmento de código:

```
print(2+2)
```

¿Puedes adivinar la salida?: Deberías de ver el número cuatro. Tómate la libertad de experimentar con otros operadores.

Sin tomar esto con mucha seriedad, has descubierto que Python puede ser utilizado como una calculadora. Tomando esto más seriamente, nos estamos adentrado en el terreno de los **operadores y expresiones**.

### Los operadores básicos

Un **operador** es un símbolo del lenguaje de programación, el cual es capaz de realizar operaciones con los valores.

Por ejemplo, como en la aritmética, el signo de `+` (más) es un operador el cual es capaz de sumar dos números, dando el resultado de la suma.

Sin embargo, no todos los operadores de Python son tan simples como el signo de más, veamos algunos de los operadores disponibles en Python, las reglas que se deben seguir para emplearlos, y como interpretar las reglas que realizan.

Se comenzará con los operadores que están asociados con las operaciones aritméticas más conocidas:

```
+, -, *, /, //, %, **
```


El orden en el que aparecen no es por casualidad. Hablaremos más de ello cuando se hayan visto todos.

Recuerda: **Cuando los datos y operadores se unen**, forman juntos **expresiones**. **La expresión más sencilla es el literal**.

### Exponenciación

Un signo de `**` (doble asterisco) es un operador de **exponenciación (potencia)**. El argumento a la izquierda es la base, el de la derecha, el exponente.

Las matemáticas clásicas prefieren una notación con superíndices, como el siguiente: 2<sup>3</sup>. Los editores de texto puros no aceptan esa notación, por lo tanto Python utiliza `**` en lugar de la notación matemática, por ejemplo, `2 ** 3`. Por ejemplo:

```
print(2 ** 3)
print(2 ** 3.)
print(2. ** 3)
print(2. ** 3.)
```

Nota: En los ejemplos, los dobles asteriscos están rodeados de espacios, no es obligatorio hacerlo pero hace que el código sea mas legible.

Los ejemplos muestran una característica importante de los operadores numéricos de Python.

Ejecuta el código y observa cuidadosamente los resultados que arroja. ¿Puedes observar algo?

Recuerda: Es posible formular las siguientes reglas con base en los resultados:

* Cuando la base y el exponente son enteros, el resultado es entero también.
* Cuando al menos, la base o el exponente es flotante, el resultado también es flotante.




    