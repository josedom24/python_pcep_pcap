# Introducción a la Programación Orientada a Objetos

La programación orientada a objetos (POO) es un enfoque de desarrollo de software que difiere del tradicional estilo de programación procedimental. 

* **Programación procedimental**: Separa los datos y las funciones en mundos distintos.
* **Programación orientada a objetos**: Combina los datos y las funciones en una sola entidad llamada **objeto**. Este enfoque es particularmente útil para proyectos grandes y complejos, ya que permite estructurar y organizar el código de manera más eficiente.

La Programación Orientado a Objetos (POO) se basa en la agrupación de objetos de distintas clases que interactúan entre sí y que, en conjunto, consiguen que un programa cumpla su propósito.

## Enfoque Procedimental vs. Enfoque Orientado a Objetos

En el enfoque procedimental, los datos y el código están separados: las variables representan datos y las funciones ejecutan acciones sobre esos datos. Sin embargo, las funciones pueden acceder a cualquier dato, lo que puede generar problemas si no se gestiona adecuadamente. Por ejemplo, una función diseñada para calcular el seno puede recibir como parámetro algo inapropiado, como el saldo de una cuenta bancaria.

Por otro lado, la programación orientada a objetos une los datos y las funciones que los manipulan dentro de una misma entidad, el **objeto**. Estos objetos son instancias de **clases**, que funcionan como plantillas o recetas para crear los objetos. Los objetos tienen **atributos (propiedades)** y **métodos (funciones específicas que pueden ejecutar)**.

## Definición de clase, objeto, atributos y métodos

* Llamamos **clase** a la representación abstracta de un concepto. Por ejemplo, "perro", "número entero" o "servidor web".
* Las clases se componen de **atributos/propiedades y métodos**.
* Un **objeto** es cada una de las instancias de una clase.
* Los **atributos o propiedades** definen las características propias del objeto y modifican su estado. Son datos asociados a las clases y a los objetos creados a partir de ellas.
* Los **métodos** son bloques de código (o funciones) de una clase que se utilizan para definir el comportamiento de los objetos.

## Ejemplo de clase y objetos

Claro, aquí tienes un ejemplo claro de clase y objeto en la Programación Orientada a Objetos (POO), junto con los conceptos de jerarquía de clases y herencia.

### Ejemplo: Sistema de Animales

**Clase**: Imagina que tienes una clase llamada `Animal`. Esta clase define las características y comportamientos generales que comparten todos los animales. En términos de POO, una clase es un **plantilla** que describe cómo debe ser un objeto.

* **Características (atributos)** de la clase `Animal`:
  * `nombre`: El nombre del animal.
  * `edad`: La edad del animal.
  * `tipo`: El tipo de animal (mamífero, ave, reptil, etc.).

* **Comportamientos (métodos)** de la clase `Animal`:
  * `hacerSonido()`: Un método que describe el sonido que hace el animal.

**Objeto**: Un objeto es una instancia de una clase. Por ejemplo, puedes crear un objeto de la clase `Animal` llamado `miPerro` con las siguientes propiedades:

* `nombre`: "Rex"
* `edad`: 5
* `tipo`: "perro"

Así, `miPerro` es un objeto que tiene las características definidas por la clase `Animal` y puede ejecutar el método `hacerSonido()`.

## Jerarquía de Clases y Herencia

**Jerarquía de clases**: En POO, las clases están organizadas en jerarquías, donde algunas clases son más específicas que otras. Por ejemplo:

* **Clase Base (superclase)**: `Animal`
  * Esta es la clase general que describe todos los animales.

* **Clases Derivadas (subclases)**:
  * `Mamifero`: Esta clase hereda de `Animal` y puede tener atributos específicos como `tipoDePelaje`.
  * `Ave`: Esta clase también hereda de `Animal` y puede tener atributos específicos como `tipoDeVuelo`.
  * `Reptil`: Similarmente, esta clase puede tener características como `tipoDeEscamas`.

**Herencia**: Uno de los pilares de la POO es la **herencia**, que permite que una clase (subclase) herede los atributos y métodos de otra clase (superclase). Esto facilita la reutilización del código y permite la creación de estructuras más complejas. Una subclase puede agregar nuevos atributos y métodos o modificar los heredados de su superclase, especializándose según sea necesario. En nuestro ejemplo:

* La clase `Mamifero` puede heredar el método `hacerSonido()` de `Animal` y también puede tener su propio método, como `darLeche()`, específico de los mamíferos.
* Cuando creas un objeto de la clase `Mamifero`, como `miGato`, este objeto tendrá todos los atributos y métodos de la clase `Animal`, pero también tendrá los métodos específicos de la clase `Mamifero`.






### Ejemplo de Clase y Objeto

Para entender cómo se crean y utilizan clases y objetos, veamos un ejemplo básico en Python:

```
class TheSimplestClass:
    pass

my_first_object = TheSimplestClass()
```

En este código, hemos definido una clase vacía llamada `TheSimplestClass`. Luego, hemos creado un objeto `my_first_object` a partir de esa clase. Este objeto es una instancia de la clase, aunque la clase no contiene ningún atributo ni método.





