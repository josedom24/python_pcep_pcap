# El módulo datetime

El módulo `datetime` en Python proporciona clases para trabajar con fechas y horas, siendo fundamental en diversas aplicaciones. La fecha y la hora tienen múltiples usos en programación, incluyendo:

* **Registro de eventos**: Permite determinar el momento exacto en que ocurren errores críticos, facilitando la creación de registros con formatos de fecha y hora personalizados.
* **Seguimiento de cambios en bases de datos**: Ayuda a almacenar información sobre cuándo se creó o modificó un registro, siendo ideal para este propósito.
* **Validación de datos**: Permite leer la fecha y hora actuales para validar datos, como comprobar la vigencia de cupones de descuento introducidos por los usuarios.
* **Almacenamiento de información importante**: Es esencial para registrar momentos de acciones críticas, como las transferencias bancarias, asegurando que se conserve la fecha y hora de dichas transacciones.

## Obtener la fecha local actual

La clase `date`, parte del módulo `datetime`, representa una fecha compuesta por año, mes y día. Puedes obtener la fecha local actual utilizando el método `today()`. A continuación, se muestran ejemplos prácticos de cómo hacerlo.

```
from datetime import date

today = date.today()

print("Hoy:", today)
print("Año:", today.year)
print("Mes:", today.month)
print("Día:", today.day)
```

Este código devuelve un objeto `date` que representa la fecha local actual, mostrando también sus atributos: año, mes y día. Cabe destacar que estos atributos son de solo lectura.

## Crear un objeto de tipo `date`

### A partir del año, mes y día

Puedes crear un objeto `date` pasando el año, mes y día como parámetros:

```
from datetime import date

my_date = date(2019, 11, 4)
print(my_date)
```

Al crear un objeto `date`, debes tener en cuenta ciertas restricciones para los parámetros:

* **Año**: debe ser mayor o igual a 1 y menor o igual a 9999.
* **Mes**: debe estar entre 1 y 12.
* **Día**: debe ser mayor o igual a 1 y menor o igual al último día del mes y año especificados.

### A partir de una marca de tiempo

También podemos crear un objeto `date` a partir de una marca de tiempo. En Linux, una marca de tiempo representa el número de segundos transcurridos desde el 1 de enero de 1970 a las 00:00:00 (UTC), conocida como la época Unix.

Para crear un objeto de fecha a partir de una marca de tiempo, utilizamos el método `fromtimestamp()`. La marca de tiempo puede obtenerse usando el módulo `time`, que proporciona la función `time()`, la cual devuelve los segundos desde la época Unix en forma de número flotante.

Aquí tienes un ejemplo de cómo hacerlo:

```
from datetime import date
import time

timestamp = time.time()
print("Marca de tiempo:", timestamp)

d = date.fromtimestamp(timestamp)
print("Fecha:", d)
```

Al ejecutar este código, primero se imprime la marca de tiempo actual y luego se convierte en un objeto `date`, mostrando la fecha correspondiente. Si ejecutas el código varias veces, notarás que la marca de tiempo aumenta, reflejando el paso del tiempo. Ten en cuenta que el resultado puede variar según la plataforma, ya que los segundos intercalares no se cuentan en sistemas Linux y Windows.

### A partir de una fecha en formato ISO

El módulo `datetime` en Python ofrece varios métodos para crear un objeto de tipo `date`, uno de los cuales es `fromisoformat()`. Este método permite crear un objeto `date` a partir de una cadena de texto que sigue el formato ISO 8601, que representa la fecha en el formato `AAAA-MM-DD`.

El estándar ISO 8601 especifica cómo deben representarse la fecha y la hora, y es ampliamente utilizado en aplicaciones y bases de datos. Para formar correctamente una fecha en este formato, se deben usar cuatro dígitos para el año (`AAAA`), dos para el mes (`MM`) y dos para el día (`DD`). Si el mes o el día son menores que 10, deben precederse con un cero.

A continuación, un ejemplo de cómo crear un objeto `date` utilizando el método `fromisoformat()`:

```
from datetime import date

d = date.fromisoformat('2019-11-04')
print(d)
```

## Modificación de una fecha

En ocasiones, es necesario modificar el año, el mes o el día de un objeto `date` en Python. Sin embargo, como los atributos `year`, `month` y `day` son de solo lectura, no se pueden cambiar directamente. En su lugar, se puede utilizar el método `replace()`.

El método `replace()` permite crear un nuevo objeto `date` con valores modificados para el año, mes o día. Este método toma como parámetros los nuevos valores que se desean asignar y devuelve un nuevo objeto `date` sin modificar el original. Los parámetros son opcionales, lo que significa que se puede modificar solo uno, dos o los tres valores a la vez.

A continuación se muestra un ejemplo que ilustra cómo utilizar el método `replace()`:

```
from datetime import date

d = date(1991, 2, 5)
print(d)  # Imprime: 1991-02-05

d = d.replace(year=1992, month=1, day=16)
print(d)  # Imprime: 1992-01-16
```

En este ejemplo, se crea inicialmente un objeto `date` correspondiente al 5 de febrero de 1991. Luego, se utiliza el método `replace()` para cambiar la fecha a 16 de enero de 1992, y el resultado se imprime en la consola. Recuerda que es importante asignar el resultado de `replace()` a una variable, ya que este método no modifica el objeto original.

## Calcular el día de la semana

El módulo `datetime` en Python proporciona métodos útiles para determinar el día de la semana de un objeto `date`. Dos de estos métodos son `weekday()` e `isoweekday()`.

El método `weekday()` devuelve el día de la semana como un número entero (0: Lunes, 1: Martes, ...)

```
from datetime import date
d = date(2019, 11, 4)  # 4 de noviembre de 2019
print(d.weekday())      # Salida: 0 (Lunes)
```

El método `isoweekday()` devuelve el día de la semana también como un número entero, pero con una numeración diferente: (1: Lunes, 2: Martes, ...)

```
from datetime import date
d = date(2019, 11, 4)  # 4 de noviembre de 2019
print(d.isoweekday())   # Salida: 1 (Lunes)
```

Aunque ambos métodos devuelven el día de la semana, difieren en su numeración. El método `weekday()` sigue la convención de comenzar con 0 para el Lunes, mientras que `isoweekday()` sigue la especificación ISO 8601 comenzando con 1. Esto permite una flexibilidad en la manera en que se puede trabajar con días de la semana según las necesidades específicas de la aplicación.

