# Prueba intermedia

1. Sabiendo que una función llamada `fun()` reside dentro de un módulo llamado `mod`, selecciona la forma correcta de importarlo.

    * `from fun import mod`
    * `import fun from mod`
    * `import fun`
    * `from mod import fun`

2. Sabiendo que una función llamada `fun()` reside dentro de un módulo llamado `mod`, y se ha importado usando la siguiente línea: `import mod`. Selecciona la forma en que se puede invocar desde tu código.

    * `fun()`
    * `mod::fun()`
    * `mod.fun()`
    * `mod‑>fun()`

3. Una función que devuelve una lista de todas las entidades disponibles en un módulo lleva por nombre:

    * `dir()`
    * `entities()`
    * `listmodule()`
    * `content()`

4. Un archivo `pyc` contiene:

    * Un intérprete de Python
    * Un compilador de Python
    * Código fuente de Python
    * Código compilado de Python

5. Cuando se importa un módulo, su contenido:

    * Es ignorado
    * Puede ser ejecutado (explícitamente)
    * Se ejecuta una vez (implícitamente)
    * Se ejecuta tantas veces como se importe

6. Una variable predefinida de Python que almacena el nombre del módulo actual lleva por nombre:

    * `__mod__`
    * `__name__`
    * `__modname__`
    * `__module__`

7. La siguiente línea de código: `from a.b import c`, causa la importación de:

    * La entidad a del módulo b del paquete c
    * La entidad b del módulo a del paquete c
    * La entidad c del módulo b del paquete a
    * La entidad c del módulo a del paquete b

8. ¿Cuál es el valor esperado asignado a la variable `result` después de que se ejecute el siguiente código?

    ```
    import math
    result = math.e != math.pow(2, 4)
    print(int(result))
    ```

    * `1`
    * `True`
    * `0`
    * `False`

9. ¿Cuál es el resultado esperado del siguiente código?

    ```
    from random import randint
    for i in range(2):
       print(randint(1, 2), end='')
    ```    

    * Existen millones de combinaciones posibles y no se puede predecir el resultado exacto.
    * 12, o 21
    * 12
    * 11, 12, 21, o 22

10. Selecciona las sentencias verdaderas. (Selecciona dos respuestas)


    * [ ] La función version del módulo platform devuelve una cadena con la versión de tu sistema operativo.
    * [ ] La función version del módulo platform devuelve una cadena con la versión de tu instalación de Python.
    * [ ] La función system del módulo platform devuelve una cadena con el nombre del sistema operativo.
    * [ ] La función processor del módulo platform devuelve un número entero con la cantidad de procesos que se están ejecutando actualmente en tu sistema operativo.

11. Durante la primera importación de un módulo, Python despliega los archivos `pyc` en el directorio llamado:

    * `Hashbang`
    * `__pycache__`
    * `__init__`
    * `Mymodules`

12. El conjunto de caracteres escrito como `#!` se emplea para:

    * Decirle a un sistema operativo MS Windows cómo ejecutar el contenido de un archivo Python
    * Decirle a un sistema operativo Unix (como Linux) cómo ejecutar el contenido de un archivo Python
    * Hacer que una entidad de módulo en particular sea privada
    * Crear un docstring (cadena de documentación)

13. Se puede obtener una lista de las dependencias de los paquetes en pip empleando el comando:

    * `deps`
    * `show`
    * `list`
    * `dir`

14. El comando `pip list` presenta una lista de:

    * Paquetes instalados localmente
    * Comandos pip disponibles
    * Paquetes locales obsoletos
    * Todos los paquetes disponibles en PyPI

15. ¿Cuáles de las siguientes sentencias son verdaderas acerca del comando `pip show`? (Selecciona dos respuestas)

    * [ ] Muestra información de cuelquier paquete en PyPI
    * [ ] Busca en todos los paquetes de PyPI
    * [ ] Sólo muestra información de los paquetes instalados
    * [ ] Nos da información del directorio donde está instalado el paquete

16. ¿Cuáles de las siguientes sentencias son verdaderas acerca del comando `pip install`? (Selecciona dos respuestas)

    * [ ] Instala un paquete en todo el sistema cuando la opción --system es especificada.
    * [ ] Siempre instala la versión más reciente del paquete y eso no se puede cambiar.
    * [ ] Instala un paquete por usuario cuando la opción --user es especificada.
    * [ ] Permite al usuario instalar una versión específica del paquete.

17. ¿Cuál de las siguientes sentencias es verdadera acerca de la actualización de paquetes de Python ya instalados?

    * Es un proceso automático que no requiere la atención del usuario.
    * Es realizada por el comando install acompañado de la opción `-U`.
    * Solo se puede hacer desinstalando e instalando los paquetes una vez más.
    * Se puede hacer reinstalando el paquete usando el comando `reinstall`.

18. ¿Qué comando de pip se puede emplear para eliminar un paquete instalado?

    * `pip uninstall package`
    * `pip install --uninstall package`
    * `pip --uninstall package`
    * `pip remove package`