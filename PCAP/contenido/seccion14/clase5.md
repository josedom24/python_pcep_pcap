# El módulo datetime en profundidad

El módulo `datetime` en Python permite trabajar con fechas y horas, ofreciendo la posibilidad de representarlas como objetos separados o combinados en uno solo. La clase principal que combina fecha y hora es `datetime`, cuyo constructor acepta varios parámetros que definen cada aspecto del objeto.

## Parámetros del constructor de `datetime`

Al crear un objeto `datetime`, se deben proporcionar los siguientes parámetros:

* **year**: El año debe estar en el rango de 1 a 9999.
* **month**: El mes debe ser un valor entre 1 y 12.
* **day**: El día debe estar comprendido entre 1 y el último día del mes correspondiente.
* **hour**: La hora debe estar entre 0 y 23.
* **minute**: El minuto debe estar entre 0 y 59.
* **second**: El segundo debe estar entre 0 y 59.
* **microsecond**: Los microsegundos deben estar entre 0 y 999999.
* **tzinfo**: Este parámetro define la zona horaria y puede ser una subclase de `tzinfo` o `None`.
* **fold**: Un valor opcional que puede ser 0 o 1, utilizado para distinguir momentos ambiguos durante los cambios de horario (por defecto es 0).

Para entender mejor el uso de la clase `datetime`, veamos un ejemplo que crea un objeto `datetime` que representa el 4 de noviembre de 2019 a las 14:53:

```
from datetime import datetime

dt = datetime(2019, 11, 4, 14, 53)

print("Fecha y Hora:", dt)
print("Fecha:", dt.date())
print("Hora:", dt.time())
```

En este ejemplo, el objeto `datetime` almacena tanto la fecha como la hora en un solo objeto. Luego, se utilizan dos métodos para extraer información específica:
* **date()**: Devuelve solo la fecha (año, mes y día).
* **time()**: Devuelve solo la hora (hora y minuto).

Todos los parámetros proporcionados en el constructor se almacenan como atributos de solo lectura, lo que asegura que una vez creado el objeto, su contenido no puede ser modificado directamente. Esto facilita el manejo preciso de fechas y horas en Python, ya que ofrece control total sobre estos elementos temporales.

## Métodos que devuelven la fecha y hora actuales

La clase `datetime` tiene varios métodos que devuelven la fecha y hora actuales. Estos métodos son:

* `today()`: devuelve la fecha y hora local actual con el atributo `tzinfo` establecido a `None`.
* `now()`: devuelve la fecha y hora local actual igual que el método `today()`, a menos que le pasemos el argumento opcional `tz`. El argumento de este método debe ser un objeto de la subclase `tzinfo`.
* `utcnow()`: devuelve la fecha y hora UTC actual con el atributo `tzinfo` establecido a `None`.

Ejemplo: 
```
from datetime import datetime

print("hoy:", datetime.today())
print("ahora:", datetime.now())
print("utc_ahora:", datetime.utcnow())
```

Como puedes ver, el resultado de los tres métodos es el mismo. Las pequeñas diferencias se deben al tiempo transcurrido entre llamadas posteriores.

## Obtener marca de tiempo

El módulo `datetime` proporciona un método llamado `timestamp` que devuelve la marca de tiempo como un número flotante. El resultado es el número de segundos que han transcurrido entre la fecha y hora especificadas por el objeto `datetime` y el 1 de enero de 1970.

Veamos un ejemplo:

```
from datetime import datetime

dt = datetime(2020, 10, 4, 14, 55)
print("Marca de tiempo:", dt.timestamp())
```

## Formato de fecha

El módulo `datetime` en Python proporciona un método clave llamado `strftime`, que permite formatear fechas y horas según nuestras necesidades. Este método devuelve una cadena con la fecha y/o la hora en el formato especificado mediante una serie de **directivas**.

Una **directiva** es una combinación del símbolo `%` seguido de una letra, que representa una parte específica de la fecha o la hora. Al usar el método `strftime`, estas directivas se reemplazan por los valores correspondientes del objeto `datetime` o `date`. Por ejemplo:
* `%Y`: Representa el año con el siglo, como un número decimal (por ejemplo, 2020).
* `%m`: Representa el mes como un número decimal con relleno de ceros si es necesario (por ejemplo, 01 para enero).
* `%d`: Representa el día del mes como un número decimal con relleno de ceros (por ejemplo, 04).

A continuación, se muestra un ejemplo de cómo usar `strftime` para formatear una fecha:

```
from datetime import date

d = date(2020, 1, 4)
print(d.strftime('%Y/%m/%d'))
```

En este caso, la fecha se ha formateado usando las directivas `%Y`, `%m`, y `%d`, separadas por el carácter `/`. Esto produce una salida con el año, mes y día, cada uno en el formato deseado. Además, puedes usar cualquier carácter separador, como `-`, `.` o incluso palabras, para personalizar el formato.

Nota: Puedes encontrar todas las directivas disponibles: [aquí](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes).

## Formato de hora

Al igual que el formato de fecha, el formato de hora en Python se realiza utilizando el método `strftime`, junto con las **directivas** correspondientes para representar las diferentes partes de la hora. En esta segunda parte, nos enfocamos en las directivas que permiten dar formato tanto a horas como a fechas combinadas.

Para formatear una hora, se utilizan directivas específicas para las horas, minutos y segundos. A continuación, algunas de las más comunes:
- **%H**: Representa la hora en formato de 24 horas (con relleno de ceros si es necesario).
- **%M**: Representa los minutos como un número decimal con relleno de ceros.
- **%S**: Representa los segundos como un número decimal con relleno de ceros.

Veamos un ejemplo:

```
from datetime import time

t = time(14, 53)
print(t.strftime("%H:%M:%S"))
```

## Formato combinado de fecha y hora

El método `strftime` también puede formatear una fecha y hora en combinación. A continuación, se muestran nuevas directivas que pueden ser útiles:
- **%y**: Representa el año en dos dígitos (por ejemplo, `20` para 2020).
- **%B**: Representa el nombre completo del mes (por ejemplo, "November").
- **%d**: Representa el día del mes como un número decimal con relleno de ceros.
  
Estas directivas se pueden combinar con las de hora para formar un formato completo.

Veamos un ejemplo:

```
from datetime import datetime

dt = datetime(2020, 11, 4, 14, 53)
print(dt.strftime("%y/%B/%d %H:%M:%S"))
```

## La función `strftime()` en el módulo `time`

El módulo `time` de Python también incluye la función `strftime()`, que permite formatear fechas y horas de manera similar a lo que hemos visto en el módulo `datetime`. Sin embargo, la versión de `strftime()` en el módulo `time` tiene una característica adicional: puede tomar opcionalmente una tupla o un objeto `struct_time` como argumento. Si no se proporciona este argumento, la función utiliza la hora local actual para el formateo.

* **Formato**: Al igual que en el módulo `datetime`, el primer argumento de `strftime()` es una cadena de formato que contiene directivas como `%Y`, `%m`, `%d`, `%H`, `%M`, `%S`, entre otras.
* **Objeto `struct_time` o tupla** (opcional): Si se proporciona, la función formatea la fecha y hora correspondientes a este objeto. Si no se pasa, se utiliza la hora local del sistema.

Veamos un ejemplo:

```
import time

timestamp = 1572879180  # Ejemplo de marca de tiempo
st = time.gmtime(timestamp)

# Formatear usando un objeto struct_time
print(time.strftime("%Y/%m/%d %H:%M:%S", st))

# Formatear la hora local actual
print(time.strftime("%Y/%m/%d %H:%M:%S"))
```
Aunque la función `strftime()` en el módulo `time` es similar a los métodos equivalentes en el módulo `datetime`, la diferencia clave es que el módulo `time` puede trabajar directamente con objetos `struct_time` y marcas de tiempo (timestamps). Esto lo hace útil cuando se manejan tiempos basados en la época Unix.

## El método `strptime()` en Python

El método `strptime()` de la clase `datetime` en el módulo `datetime` es la contraparte de `strftime()`, pero en lugar de formatear una fecha a una cadena, convierte una cadena que representa una fecha y hora en un objeto `datetime`. Esto es útil cuando se trabaja con fechas en formato de texto que necesitan ser convertidas a un formato de objeto manejable en Python.

Para usar `strptime()`, se deben proporcionar dos argumentos obligatorios:
1. **Cadena**: La cadena que representa una fecha y hora.
2. **Formato**: El formato en el que se ha guardado la cadena, utilizando directivas similares a las que se usan con `strftime()`.

El formato especificado debe coincidir exactamente con la estructura de la cadena de fecha, de lo contrario, se lanzará una excepción `ValueError`.

Ejemplo:

```
from datetime import datetime

# Convertir cadena a objeto datetime usando strptime
fecha_hora = datetime.strptime("2019/11/04 14:53:00", "%Y/%m/%d %H:%M:%S")
print(fecha_hora)
```

### Uso de `strptime()` en el módulo `time`

El módulo `time` también incluye una función `strptime()` que funciona de manera análoga, pero en lugar de devolver un objeto `datetime`, devuelve un objeto `struct_time`. El uso es similar al de la clase `datetime`, pero el resultado será diferente:

```
import time

# Convertir cadena a objeto struct_time usando strptime
fecha_hora_struct = time.strptime("2019/11/04 14:53:00", "%Y/%m/%d %H:%M:%S")
print(fecha_hora_struct)
```
Este resultado es un objeto `struct_time`, que contiene detalles sobre la fecha y hora, junto con información adicional como el día de la semana (`tm_wday`), el día del año (`tm_yday`), y si la hora de verano está en efecto (`tm_isdst`).


