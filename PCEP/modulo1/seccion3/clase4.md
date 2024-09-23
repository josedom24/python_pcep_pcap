# Cómo estropear y arreglar tu código

## Cómo estropear y arreglar tu código

Ahora ejecuta IDLE nuevamente.

* Haz clic en *File*, *Open*, señala el archivo que guardaste anteriormente y deja que IDLE lo lea de nuevo.
* Intenta ejecutarlo de nuevo presionando *F5* cuando la ventana del editor esté activa.

Veamos alguna características del editor:

* Si quitas el último paréntesis y lo vuelves a escribir, el editor resalta el texto que hay entre paréntesis.

    ![python3](img/python8.png)

    Cada vez que coloques el paréntesis de cierre en tu programa, IDLE mostrará la parte del texto limitada con un par de paréntesis correspondientes. Esto te ayuda a recordar **colocarlos en pares**.

* Retira nuevamente el paréntesis de cierre. El código se vuelve erróneo. Ahora contiene un error de sintaxis. IDLE no debería dejar que lo ejecutes.

    Intenta ejecutar el programa de nuevo. IDLE te recordará que guardes el archivo modificado. Sigue las instrucciones.

    Al intentar ejecutar el código, elIDLE te dará un **error** porque ha detectado que el programa no se ha terminado de escribir.

    ![python3](img/python9.png)

    Arregla el código, escribiendo el paréntesis final y vuelve a ejecutar el programa.

* Ahora, vamos a provocar otro error: elimina una letra de la palabra `print`. Ejecuta el código presionando *F5*. Como puedes ver, Python no puede reconocer la instrucción (no la colorea).

    ![python3](img/python10.png)

    Hemos introducido un error sintáctico, por lo que el error que nos aparece el distinto al anterior. Esto se debe a que la naturaleza del error es diferente y el error se descubre en una etapa diferente de la interpretación.

    ![python3](img/python11.png)

    La ventana del editor no proporcionará ninguna información útil sobre el error, pero es posible que las ventanas de la consola si.
    
    El mensaje (en rojo) muestra (en las siguientes líneas):

    * El **rastreo o traceback** (que es la ruta que el código atraviesa a través de diferentes partes del programa, puedes ignorarlo por ahora, ya que está vacío en un código tan simple).
    * La **ubicación del error** (el nombre del archivo que contiene el error, el número de línea y el nombre del módulo); nota: el número puede ser engañoso, ya que Python generalmente muestra el lugar donde se percata por primera vez de los efectos del error, no necesariamente del error en sí.
    * El **contenido de la línea errónea**. Podemos configurar la ventana del editor para que muestre el número de línea y que sea más fácil posicionarnos en el error.
    * El **nombre del error y una breve explicación**.
