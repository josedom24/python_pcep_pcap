# El módulo time

## Creación de objetos `time`

El módulo `datetime` de Python también incluye la clase `time`, que se utiliza para representar la hora. Esta clase permite crear objetos que encapsulan información sobre horas, minutos, segundos y microsegundos.

El constructor de la clase `time` acepta los siguientes parámetros:

- **hour**: (0-23) Hora del día.
- **minute**: (0-59) Minuto de la hora.
- **second**: (0-59) Segundo del minuto.
- **microsecond**: (0-999999) Microsegundo del segundo.
- **tzinfo**: (opcional) Un objeto de la subclase `tzinfo` que proporciona información sobre la zona horaria, o `None` (por defecto).
- **fold**: (opcional) Debe ser 0 o 1, con un valor predeterminado de 0, que se utiliza para representar ambigüedades en los cambios de hora.

Aquí hay un ejemplo que muestra cómo crear un objeto de tipo `time`:

```
from datetime import time

# Creando un objeto de tipo time
t = time(14, 53, 20, 1)

# Mostrando el tiempo y sus componentes
print("Tiempo:", t)                      # Salida: Tiempo: 14:53:20.000001
print("Hora:", t.hour)                   # Salida: Hora: 14
print("Minuto:", t.minute)               # Salida: Minuto: 53
print("Segundo:", t.second)               # Salida: Segundo: 20
print("Microsegundo:", t.microsecond)     # Salida: Microsegundo: 1
```

* Puedes acceder a los componentes individuales de la hora (hora, minuto, segundo, microsegundo) utilizando los atributos correspondientes de la instancia del objeto `time`.
* El parámetro `tzinfo` y el parámetro `fold` están relacionados con la gestión de zonas horarias y el manejo de la ambigüedad en los cambios de hora, aunque no se cubrirán en este curso.

## El módulo `time`

### Resumen sobre el Módulo `time` en Python

El módulo `time` de Python proporciona diversas funciones para trabajar con el tiempo y las pausas en la ejecución de programas. Uno de los usos más comunes de este módulo es la función `sleep`, que permite suspender la ejecución de un programa durante un número específico de segundos.

La función `sleep` se utiliza para pausar la ejecución del programa por un período determinado. Acepta un argumento que puede ser un número entero o de punto flotante, representando los segundos de pausa.

A continuación, se muestra un ejemplo de cómo se puede utilizar la función `sleep` para simular que un estudiante toma una siesta corta:

```
import time

class Student:
    def take_nap(self, seconds):
        print("Estoy muy cansado. Tengo que echarme una siesta. Hasta luego.")
        time.sleep(seconds)  # Suspende la ejecución durante el número de segundos especificado
        print("¡Dormí bien! ¡Me siento genial!")

# Creando una instancia de la clase Student y llamando al método take_nap
student = Student()
student.take_nap(5)  # La siesta dura 5 segundos
```
* Puedes modificar la duración de la siesta cambiando el valor pasado a la función `take_nap`. Por ejemplo, si deseas que la siesta dure 10 segundos, simplemente reemplaza `5` por `10`.
* La función `sleep` es útil no solo para simular tiempos de espera, sino también para controlar la ejecución de programas que requieren intervalos específicos entre operaciones.

## La función `ctime()`

La función `ctime()` del módulo `time` en Python se utiliza para convertir un valor de tiempo en segundos desde el 1 de enero de 1970 (época Unix) en una representación de cadena legible que muestra la fecha y hora correspondientes.

* **Con un Timestamp:** Si proporcionas un timestamp como argumento, `ctime()` devolverá una cadena que representa la fecha y hora correspondientes a ese timestamp.
* **Sin Argumento:** Si llamas a `ctime()` sin argumentos, devuelve la fecha y hora actual.

Aquí hay un ejemplo de cómo usar la función `ctime()`:

```
import time

# Marca de tiempo específica (en segundos desde la época Unix)
timestamp = 1572879180
print(time.ctime(timestamp))  # Convierte la marca de tiempo a una cadena legible
```

Esto indica que el timestamp `1572879180` corresponde al 4 de noviembre de 2019 a las 14:53:00.

Veamos otro ejemplo para calcular la hora actual:

```
import time

print(time.ctime())  # Muestra la fecha y hora actuales
```

## Las funciones `gmtime()` y `localtime()`

En el módulo `time` de Python, las funciones `gmtime()` y `localtime()` son útiles para convertir un valor de tiempo en segundos desde la época Unix a un objeto `struct_time`, que descompone el tiempo en componentes legibles como año, mes, día, etc.

Antes de ver cómo funcionan estas funciones, aquí tienes un resumen de la clase `struct_time` y sus atributos:

```
time.struct_time:
    tm_year   # Año (por ejemplo, 2024)
    tm_mon    # Mes (1 a 12)
    tm_mday   # Día del mes (1 a 31)
    tm_hour   # Hora (0 a 23)
    tm_min    # Minuto (0 a 59)
    tm_sec    # Segundo (0 a 61)
    tm_wday   # Día de la semana (0 = Lunes, 6 = Domingo)
    tm_yday   # Día del año (1 a 366)
    tm_isdst  # Horario de verano (1: sí, 0: no, -1: desconocido)
    tm_zone   # Nombre de la zona horaria (abreviado)
    tm_gmtoff # Desplazamiento UTC en segundos
```

* La función `gmtime()` convierte un timestamp en segundos a `struct_time` en el tiempo UTC (Tiempo Universal Coordinado). El atributo `tm_isdst` siempre será 0 porque no aplica el horario de verano.
* La función `localtime()` convierte un timestamp en segundos a `struct_time` en la hora local del sistema. Puede mostrar un valor distinto para `tm_isdst` dependiendo de si se está aplicando el horario de verano.

Aquí hay un ejemplo que muestra cómo usar ambas funciones:

```
import time

# Timestamp específico
timestamp = 1572879180

# Convertir a UTC
utc_time = time.gmtime(timestamp)
print(utc_time)

# Convertir a hora local
local_time = time.localtime(timestamp)
print(local_time)
```

## Las funciones `asctime()` y `mktime()`

El módulo `time` de Python incluye funciones que permiten trabajar con objetos `struct_time` y tuplas, facilitando la conversión entre formatos de tiempo legibles y timestamps en segundos desde la época Unix.

* La función `asctime()` convierte un objeto `struct_time` o una tupla que representa el tiempo en una cadena en un formato legible. Si no se proporciona un argumento, utiliza el tiempo devuelto por la función `localtime()`.
* La función `mktime()` convierte un objeto `struct_time` o una tupla que expresa la hora local al número de segundos desde la época Unix.

El formato de la tupla con la que vamos a trabajr tiene la siguiente estructura:

1. `tm_year` (año)
2. `tm_mon` (mes, 1-12)
3. `tm_mday` (día del mes, 1-31)
4. `tm_hour` (hora, 0-23)
5. `tm_min` (minuto, 0-59)
6. `tm_sec` (segundo, 0-59)
7. `tm_wday` (día de la semana, 0-6)
8. `tm_yday` (día del año, 1-366)
9. `tm_isdst` (horario de verano, 1: sí, 0: no, -1: desconocido)

A continuación se muestra un ejemplo que ilustra cómo usar ambas funciones:

```
import time

# Timestamp específico
timestamp = 1572879180

# Obtener struct_time en UTC
st = time.gmtime(timestamp)

# Convertir struct_time a cadena legible
print(time.asctime(st))

# Convertir tupla a timestamp
timestamp_from_tuple = time.mktime((2019, 11, 4, 14, 53, 0, 0, 308, 0))
print(timestamp_from_tuple)
```

