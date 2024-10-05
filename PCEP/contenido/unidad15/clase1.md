# Tipos de datos secuencias y mutabilidad

Los **tipos de datos secuencia** son aquellos que nos permiten almacenar más de un valor (o ninguno si la secuencia esta vacía). Estos tipos de datos pueden ser recorridos accediendo a cada elemento de los guardados.

Podemos decir que una secuencia es un tipo de dato que puede ser escaneado por el bucle `for`.
Hasta ahora hemos trabajado con tipos de datos secuencias, como son las listas y las cadenas de caracteres. En estos apartados trabajaremos, además, con las **tuplas**.

Por otro lado, la **mutabilidad** es la propiedad de cualquier tipo de dato en Python que describe su disponibilidad para poder cambiar libremente durante la ejecución de un programa. Existen dos tipos de datos en Python: **mutables e inmutables**.

* Los **datos mutables** pueden ser actualizados o modificados libremente en cualquier momento, por ejemplo hemos estudiado que las listas y los diccionarios son mutables.
* Los **datos inmutables** no pueden ser modificados de esta manera. Este tipo de datos sólo pueden ser asignadas y leídas, so se le puede añadir o eliminar ningún elemento guardado. Si queremos añadir nuevos elementos habrá que crear un nuevo dato modificado con ese nuevo elemento. A este tipo de datos corresponden las tuplas y las cadenas de caracteres.

También vamos a trabajar con un tipo de dato llamado **diccionario**, no es un tipo de dato secuencia, podemos decir que es un **tipo de datos mapa**, ya que cada dato guardado se referencia con una clave. Los diccionarios se pueden adaptarse fácilmente a un procesamiento secuencial y además son mutables.