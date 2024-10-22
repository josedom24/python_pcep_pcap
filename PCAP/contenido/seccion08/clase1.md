# Introducción a la Programación Orientada a Objetos en Python

La programación orientada a objetos (POO) es un enfoque de desarrollo de software que difiere del tradicional estilo de programación procedimental. En lugar de separar los datos y las funciones en mundos distintos, POO los combina en una sola entidad llamada "objeto". Este enfoque es particularmente útil para proyectos grandes y complejos, ya que permite estructurar y organizar el código de manera más eficiente.

## Enfoque Procedimental vs. Enfoque Orientado a Objetos

En el enfoque procedimental, los datos y el código están separados: las variables representan datos y las funciones ejecutan acciones sobre esos datos. Sin embargo, las funciones pueden acceder a cualquier dato, lo que puede generar problemas si no se gestiona adecuadamente. Por ejemplo, una función diseñada para calcular el seno puede recibir como parámetro algo inapropiado, como el saldo de una cuenta bancaria.

Por otro lado, la programación orientada a objetos une los datos y las funciones que los manipulan dentro de una misma entidad, el "objeto". Estos objetos son instancias de "clases", que funcionan como plantillas o recetas para crear los objetos. Los objetos tienen atributos (propiedades) y métodos (funciones específicas que pueden ejecutar).

## Jerarquía de Clases

En POO, las clases están organizadas en jerarquías. Por ejemplo, pensemos en los vehículos: todos tienen en común que pueden moverse, pero dentro de esa categoría general, podemos especializarlos en vehículos terrestres, acuáticos, aéreos y espaciales. Esta especialización crea lo que se llama subclases, que heredan las propiedades y métodos de la clase más general o superclase, pero pueden agregar sus propias características.

### Ejemplo de Jerarquía de Vehículos
- **Vehículos** (superclase)
  - **Vehículos Terrestres** (subclase)
    - Vehículos con ruedas
    - Vehículos con pistas
    - Aerodeslizadores
  - **Vehículos Acuáticos**
  - **Vehículos Aéreos**
  - **Vehículos Espaciales**

Este mismo concepto se aplica a la POO, donde los objetos pueden pertenecer a clases generales y a subclases más específicas.

## Definición de una Clase y un Objeto

Una clase es un conjunto de objetos que comparten características comunes. Un objeto es una instancia concreta de una clase y hereda todos sus atributos y métodos. En POO, los objetos pueden ser miembros de múltiples clases al mismo tiempo, siguiendo la jerarquía definida.

### Ejemplo de Clase y Objeto

Para entender cómo se crean y utilizan clases y objetos, veamos un ejemplo básico en Python:

```
class TheSimplestClass:
    pass

my_first_object = TheSimplestClass()
```

En este código, hemos definido una clase vacía llamada `TheSimplestClass`. Luego, hemos creado un objeto `my_first_object` a partir de esa clase. Este objeto es una instancia de la clase, aunque la clase no contiene ningún atributo ni método.

## Herencia

Uno de los pilares de la POO es la **herencia**, que permite que una clase (subclase) herede los atributos y métodos de otra clase (superclase). Esto facilita la reutilización del código y permite la creación de estructuras más complejas. Una subclase puede agregar nuevos atributos y métodos o modificar los heredados de su superclase, especializándose según sea necesario.

