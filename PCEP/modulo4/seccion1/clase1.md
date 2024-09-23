# Módulo 4: Funciones, Tuplas, Diccionarios, Excepciones y Procesamiento de Datos
## Sección 1: Funciones
## Clase: Introducción a las funciones

## ¿Por qué necesitamos las funciones?

* Hasta ahora hemos utilizado distintas funciones: `print()`, `input()`, ...
* También hemos usado algunos **métodos**, que son funciones internas que poseen algunos tipos de datos, como las listas.
* En este capítulo vamos a **aprender a escribir nuestras propias funciones**.
* Cuando un código se repite mucho en nuestro programa, seguramente será necesario codificar esa funcionalidad en una función y repetir su utilización.
* De esta manera estamos **simplificando el código**, ya que si hemos cometido un error, dicho error estará en la definición de la función y no se repetirá por el código.
* Además estarás **reutilizando el código**: el código de la función se escribe una sola vez y se utiliza cada vez que lo necesitemos.
* Si el problema que estamos resolviendo es muy grande, es posible que nuestro programa sea muy extenso y poco legible. en este caso, es recomendable dividir el problema, en problemas más pequeños y cada una de estos codificarlo en una función que será más simple que el programa original. A esta técnica se llama **divide y vencerás** o **descomposición**.
* Esto **simplifica** considerablemente el trabajo del programa, debido a que cada función se codifica por separado, y consecuentemente se prueba por separado. 

## Descomposición

* La **descomposición** nos permite descomponer el problema que estamos resolviendo, en subproblemas más pequeños. Estos, asu vez, se pueden dividir aún más. Cad problema más simple se codificará en distintas funciones.
* esta técnica favorece el trabajo del equipo de desarrollo. A cada desarrollador se le puede asignar hacer parte del programa: codificar una función.
* Además de compartir el trabajo, se comparte la responsabilidad entre varios desarrolladores.
* Cada uno debe escribir un conjunto bien definido y claro de funciones, las cuales al ser combinadas dentro de un módulo (esto se clarificara un poco más adelante) nos dará como resultado el producto final.
* La **programación modular** es un paradigma de programación que consiste en dividir un programa en módulos o subprogramas con el fin de hacerlo más legible y manejable.

## ¿De dónde provienen las funciones?

* Pueden estar **definidas de forma predeterminada en Python**. Por ejemplo, la función `print()`. Estas funciones son **parte integral** de Python, se les suele llamar **funciones integradas** y siempre se pueden usar.
* Pueden estar **definidas de uno o varios de los módulos de Python** llamados complementos o librerías; algunos de los módulos vienen con Python, otros pueden requerir una instalación por separado. Para usar estas funciones es necesario **importar el módulo**.
* **Puedes escribirlas tú mismo**, colocando tantas funciones como desees y necesites dentro de su programa para hacerlo más simple, claro y elegante.
