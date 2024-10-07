# Introducción a Python

## Introducción a Python

* Python es un lenguaje de programación de alto nivel, interpretado, orientado a objetos y de uso generalizado con semántica dinámica, que se utiliza para la programación de propósito general.
* El nombre no proviene de un tipo de serpiente, proviene de una vieja serie de comedia de la BBC llamada **Monty Python's Flying Circus**.
* Python es el trabajo de una persona. Por lo general, los grandes lenguajes de programación son desarrollados y publicados por grandes compañías que emplean a muchos profesionales.
* Python fue creado por [**Guido van Rossum**](https://en.wikipedia.org/wiki/Guido_van_Rossum), nacido en 1956 en Haarlem, Países Bajos. 
* El éxito de Python se debe al trabajo de una gran comunidad de desarrolladores.

## Los objetivos de Python

* En 1999, Guido van Rossum definió sus objetivos para Python:
    * Un **lenguaje fácil e intuitivo** tan poderoso como los de los principales competidores.
    * De **código abierto**, para que cualquiera pueda contribuir a su desarrollo.
    * El **código que es tan comprensible como el inglés simple**.
    * Adecuado para **tareas cotidianas**, permitiendo tiempos de desarrollo cortos.
* Unos 20 años después, está claro que todas estas intenciones se han cumplido. Algunas fuentes dicen que Python es el lenguaje de programación más popular del mundo, mientras que otros afirman que es el tercero o el quinto.
* Nos lo encontramos en los primeros puestos de lenguajes populares:  
    * [PYPL PopularitY of Programming Language](https://pypl.github.io/PYPL.html). 
    * [TIOBE Programming Community Index](https://www.tiobe.com/tiobe-index/).
* Python no es un lenguaje joven. Es **maduro y digno de confianza**.

## Características de Python

* Es **fácil de aprender**: el tiempo necesario para aprender Python es más corto que en muchos otros lenguajes; esto significa que es posible comenzar la programación real más rápido.
* Es **fácil de enseñar**: la carga de trabajo de enseñanza es menor que la que necesitan otros lenguajes; esto significa que el profesor puede poner más énfasis en las técnicas de programación generales (independientes del lenguaje).
* Es **fácil de utilizar para escribir software nuevo**: a menudo es posible escribir código más rápido cuando se emplea Python.
* Es **fácil de entender**: a menudo, también es más fácil entender el código de otra persona más rápido si está escrito en Python.
* Es **fácil de obtener, instalar y desplegar**: Python es gratuito, abierto y multiplataforma; no todos los lenguajes pueden presumir de eso.

## ¿Rivales de Python?

* Python tiene dos competidores directos, con propiedades y predisposiciones comparables. Estos son:
    * **Perl** - un lenguaje de scripting originalmente escrito por Larry Wall.
    * **Ruby** - un lenguaje de scripting originalmente escrito por Yukihiro Matsumoto.

* Perl es más tradicional, más conservador que Python. Su sintaxis es mucho más parecida al lenguaje de programación C clásico.
* Ruby es más innovador y funcionalidad más modernas.
* Python tiene características que lo posiciona entre estos dos lenguajes.

## Donde se usa Python

* Lo vemos todos los días y en casi todas partes. 
* **Servicios de Internet**: motores de búsqueda, almacenamiento en la nube y herramientas, redes sociales, etc. 
* Muchas **herramientas de desarrollo** se implementan en Python. Cada vez se escriben más aplicaciones de uso diario en Python.
* Ciencia de datos y análisis.
* Inteligencia artificial y machine learning.
* Modelado 3D.
* Aplicaciones de Oficina.
* Aplicaciones móviles.
* [Y muchas más...](https://wiki.python.org/moin/Applications)

No es conveniente su uso, en programación de bajo nivel (a veces llamada programación "cercana al metal"): si deseas implementar un controlador o motor gráfico extremadamente efectivo, no se usaría Python.

## Versiones de Python

* Existen dos versiones principales de Python, llamados **Python 2 y Python 3**.
* Python 2 es una versión antigua. Su desarrollo no se continúa, aunque eso no significa que no haya actualizaciones. 
* Python 3 es la versión actual del lenguaje. Se sigue desarrollando y van apareciendo nuevas subversiones cada cierto tiempo.
* Estas dos versiones de Python **no son compatibles entre sí**. Las secuencias de comandos de Python 2 no se ejecutarán en un entorno de Python 3 y viceversa.
* La tarea de **migrar código de Python2 a Python3** puede ser compleja y cara, aunque actualmente la mayoría de módulos y programas se han migrado. 
* Python 3 no es solo una versión mejorada de Python 2, es un lenguaje completamente diferente, aunque es muy similar a su predecesor. 
* Si estás modificando una solución de Python existente, entonces es muy probable que esté codificada en Python 2. Esta es la razón por la que Python 2 todavía está en uso. 
* Si se va a comenzar un nuevo proyecto de Python, deberías usar Python 3, esta es la versión de Python que se usará durante este curso.
* Es importante recordar que puede haber diferencias mayores o menores entre las siguientes versiones de Python 3. La buena noticia es que todas las versiones más nuevas de Python 3 son compatibles con las versiones anteriores de Python 3. 
* Todos los ejemplos de código que encontrarás durante el curso se han probado con Python 3.4, Python 3.6, Python 3.7, Python 3.8 y Python 3.9.
* Actualmente (Septiembre de 2024) la última versión de Python es la 3.12.

## Implementaciones de Python

* Además de Python 2 y Python 3, hay más de una versión de cada uno.
* Siguiendo la [Página wiki de Python](https://wiki.python.org/moin/PythonImplementations), una implementación de Python se refiere a "un programa o entorno que brinda soporte para la ejecución de programas escritos en el lenguaje Python, representado por la Implementación de Referencia de CPython.".
* **CPython**:
    *  Mantenido desde la **PSF ([Python Software Foundation](https://www.python.org/psf-landing/))**, una comunidad que tiene como objetivo desarrollar, mejorar, expandir y popularizar Python y su entorno. 
    * Se suele llamar Python canónico. 
    * También se consideran el Python de referencia, ya que cualquier otra implementación del lenguaje debe seguir todos los estándares establecidos por el PSF.
    * Guido van Rossum utilizó el lenguaje de programación "C" para implementar la primera versión de su lenguaje y esta decisión aún está vigente. 
    * Por esta razón Python puede ser portado y migrado fácilmente a todas las plataformas con la capacidad de compilar y ejecutar programas en lenguaje "C" (virtualmente todas las plataformas tienen esta característica, lo que abre mucha expansión y oportunidades para Python).
* **Cython**:
    * Cython es una implementación más eficiente que CPython.
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