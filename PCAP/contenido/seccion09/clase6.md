# Explorando y modificando las clases y objetos

## Reflexión e introspección en Python

En muchos lenguajes de programación orientados a objetos, Python incluido, existen dos capacidades fundamentales que ofrecen gran flexibilidad y poder al programador: la **introspección** y la **reflexión**. Estas habilidades permiten que los programas examinen y modifiquen objetos y clases durante la ejecución, lo que abre puertas a una programación más dinámica y adaptable.

* La **introspección** es la capacidad de un programa para **examinar** las propiedades, tipo o características de un objeto **en tiempo de ejecución**. En otras palabras, permite que el código explore qué es un objeto, de qué clase es, qué atributos tiene y qué métodos puede ejecutar, todo esto mientras el programa está corriendo.
* La **reflexión** va un paso más allá que la introspección. No solo permite examinar el tipo y las propiedades de un objeto en tiempo de ejecución, sino que también otorga la capacidad de **manipular** esas propiedades y funciones **dinámicamente**.

En pocas palabras, la reflexión permite modificar el comportamiento o el estado de un objeto mientras el programa está en ejecución, sin que necesitemos saber de antemano cómo está definido el objeto.

Python proporciona varias funciones integradas que permiten la introspección:

- **`type()`**: Nos indica el tipo de un objeto.
- **`dir()`**: Devuelve una lista de atributos y métodos disponibles en un objeto.
- **`hasattr()`**: Verifica si un objeto tiene un atributo o método específico.
- **`getattr()`**: Permite obtener el valor de un atributo de un objeto.
- **`isinstance()`**: Verifica si un objeto es instancia de una clase específica.


