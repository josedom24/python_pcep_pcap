# Módulo 1: Introducción a Python y a la programación de computadoras
## Sección 1: Introducción a Python
## Clase: Implementaciones de Python

### Existe más de un Python

* Existen dos tipos principales de Python, llamados Python 2 y Python 3.
* Python 2 es una versión anterior del Python original. Su desarrollo no se continúa, aunque eso no significa que no haya actualizaciones. 
* Python 3 es la versión más nueva (para ser precisos, la actual) del lenguaje. Está atravesando su propio camino de evolución.
* Estas dos versiones de Python no son compatibles entre sí. Las secuencias de comandos de Python 2 no se ejecutarán en un entorno de Python 3 y viceversa.
* La tarea de migrar código de Python2 a Python3 puede ser compleja y cara, y puede introducir nuevos errores en el programa. 
* Python 3 no es solo una versión mejorada de Python 2, es un lenguaje completamente diferente, aunque es muy similar a su predecesor. 
* Si estás modificando una solución de Python existente, entonces es muy probable que esté codificada en Python 2. Esta es la razón por la que Python 2 todavía está en uso. 
* Si se va a comenzar un nuevo proyecto de Python, deberías usar Python 3, esta es la versión de Python que se usará durante este curso.
* Es importante recordar que puede haber diferencias mayores o menores entre las siguientes versiones de Python 3 (p. Ej., Python 3.6 introdujo claves de diccionario ordenadas de forma predeterminada en la implementación de CPython). La buena noticia es que todas las versiones más nuevas de Python 3 son compatibles con las versiones anteriores de Python 3. 
* Todos los ejemplos de código que encontrarás durante el curso se han probado con Python 3.4, Python 3.6, Python 3.7, Python 3.8 y Python 3.9.
* Actualmente (Septiembre de 2024) la última versión de Python es la 3.12.

### Implementaciones de Python

* Además de Python 2 y Python 3, hay más de una versión de cada uno.
* Siguiendo la [Página wiki de Python](https://wiki.python.org/moin/PythonImplementations), una implementación de Python se refiere a "un programa o entorno que brinda soporte para la ejecución de programas escritos en el lenguaje Python, representado por la Implementación de Referencia de CPython.".
* **CPython**:
    *  Mantenido desde la **PSF ([Python Software Foundation](https://www.python.org/psf-landing/))**, una comunidad que tiene como objetivo desarrollar, mejorar, expandir y popularizar Python y su entorno. 
    * Se suele llamar Python canónico. 
    * También se consideran Pythons de referencia, ya que cualquier otra implementación del lenguaje debe seguir todos los estándares establecidos por el PSF.
    * Guido van Rossum utilizó el lenguaje de programación "C" para implementar la primera versión de su lenguaje y esta decisión aún está vigente. Todos los Pythons que provienen del PSF están escritos en el lenguaje "C". Existen muchas razones para este enfoque. Una de ellas (probablemente la más importante) es que gracias a ello, Python puede ser portado y migrado fácilmente a todas las plataformas con la capacidad de compilar y ejecutar programas en lenguaje "C" (virtualmente todas las plataformas tienen esta característica, lo que abre mucha expansión y oportunidades para Python).
* **Cython**:
    * Cython es una implementación más eficiente qye CPython.
    * Los cálculos matemáticos grandes y complejos pueden ser fácilmente codificados en Python (mucho más fácil que en "C" o en cualquier otro lenguaje tradicional), pero la ejecución del código resultante puede requerir mucho tiempo.
    * En esta implementación, el código Python se traduce a lenguaje "C", que se ejecuta más rápido que Python puro.
* **Jython**:
    * "J" es de "Java". Esta implementación de Python está escrito en Java en lugar de C. 
    * Esto es útil, por ejemplo, si desarrollas sistemas grandes y complejos escritos completamente en Java y deseas agregarles cierta flexibilidad de Python.
    * Jython puede comunicarse con la infraestructura Java existente de manera más efectiva. Es por esto que algunos proyectos lo encuentran útil y necesario.
    * Nota: la implementación actual de Jython sigue los estándares de Python 2. Hasta ahora, no hay Jython conforme a Python 3.
* **PyPy y RPython**:
    *  Python dentro de un Python. Esta implementación es un entorno de Python escrito en un lenguaje similar a Python llamado RPython (Restricted Python). En realidad es un subconjunto de Python.
    * El código fuente de PyPy no se interpreta, sino que se traduce al lenguaje de programación C y luego se ejecuta por separado.
    * Esto es útil porque si deseas probar cualquier característica nueva que pueda ser o no introducida en la implementación de Python, es más fácil verificarla con PyPy que con CPython. Esta es la razón por la que PyPy es más una herramienta para las personas que desarrollan Python que para el resto de los usuarios.