# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 1: El Programa "¡Hola, Mundo!"
## Clase: LABORATORIO - Dando forma a la salida

### Tiempo Estimado

5-15 minutos

### Nivel de Dificultad

Fácil

### Objetivos

* Experimentar con el código Python existente.
* Descubrir y solucionar errores básicos de sintaxis.
* Familiarizarse con la función `print()` y sus capacidades de formato.

### Escenario

Con el siguiente programa:

```
print("    *")
print("   * *")
print("  *   *")
print(" *     *")
print("***   ***")
print("  *   *")
print("  *   *")
print("  *****")
```

Recomendamos que juegues con el código que hemos escrito para ti y que realices algunas correcciones (quizás incluso destructivas). Siéntete libre de modificar cualquier parte del código, pero hay una condición: aprende de tus errores y saca tus propias conclusiones.

Intenta:

* Minimizar el número de invocaciones de la función `print()` insertando la secuencia `\n` en las cadenas.
* Hacer la flecha dos veces más grande (pero mantener las proporciones).
* Duplicar la flecha, colocando ambas flechas lado a lado; nota: una cadena se puede multiplicar usando el siguiente truco: `"cadena" * 2` producirá `cadenacadena` (te contaremos más sobre ello pronto).
* Elimina cualquiera de las comillas y observa detenidamente la respuesta de Python; presta atención a donde Python ve un error: ¿es el lugar en donde realmente existe el error?
* Haz lo mismo con algunos de los paréntesis.
* Cambia cualquiera de las palabras print en otra cosa (por ejemplo de minúscula a mayúscula, Print) - ¿Qué sucede ahora?
* Reemplaza algunas de las comillas por apóstrofes; observa lo que pasa detenidamente.

### Salida Esperada

```
Fundamentos***Programación***en...Python
```

### Solución

```
# Sample Solution

###################
print("original version:")
###################
print("    *")
print("   * *")
print("  *   *")
print(" *     *")
print("***   ***")
print("  *   *")
print("  *   *")
print("  *****")
###################
print("with fewer 'print()' invocations:")
###################
print("    *\n   * *\n  *   *\n *     *\n***   ***")
print("  *   *\n  *   *\n  *****")
###################
print("higher:")
###################
print("        *")
print("       * *")
print("      *   *")
print("     *     *")
print("    *       *")
print("   *         *")
print("  *           *")
print(" *             *")
print("******     ******")
print("     *     *")
print("     *     *")
print("     *     *")
print("     *     *")
print("     *     *")
print("     *     *")
print("     *******")
###################
print("doubled:")
###################
print("        *        "*2)
print("       * *       "*2)
print("      *   *      "*2)
print("     *     *     "*2)
print("    *       *    "*2)
print("   *         *   "*2)
print("  *           *  "*2)
print(" *             * "*2)
print("******     ******"*2)
print("     *     *     "*2)
print("     *     *     "*2)
print("     *     *     "*2)
print("     *     *     "*2)
print("     *     *     "*2)
print("     *     *     "*2)
print("     *******     "*2)
```
