# Operaciones con fechas y horas

En Python, es común que surja la necesidad de realizar cálculos con fechas y horas, como encontrar la diferencia entre dos fechas o agregar o restar tiempo. Para ello, el módulo `datetime` incluye una clase llamada `timedelta`, diseñada específicamente para realizar estas operaciones.

Un objeto `timedelta` se puede crear automáticamente al restar dos objetos de tipo `date` o `datetime`. Al hacerlo, se obtiene un resultado que representa la diferencia en días y, si se incluye la hora, también en horas, minutos y segundos.

Veamos un ejemplo donde se restan dos objetos `date` y dos objetos `datetime`:

```
from datetime import date
from datetime import datetime

# Resta de dos objetos 'date'
d1 = date(2020, 11, 4)
d2 = date(2019, 11, 4)
print(d1 - d2)

# Resta de dos objetos 'datetime'
dt1 = datetime(2020, 11, 4, 0, 0, 0)
dt2 = datetime(2019, 11, 4, 14, 53, 0)
print(dt1 - dt2)
```

Una vez que se obtiene un objeto `timedelta`, se pueden realizar varias operaciones como sumar o restar días, horas, minutos, etc., a objetos `date` o `datetime`.

Por ejemplo:

```
from datetime import timedelta

# Crear un objeto timedelta
delta = timedelta(days=5, hours=2, minutes=30)

# Sumar timedelta a una fecha
nueva_fecha = d1 + delta
print(nueva_fecha)
```

Esto sumaría 5 días, 2 horas y 30 minutos a la fecha `d1` (2020-11-04).

## Creación de objetos `timedelta`

Un objeto `timedelta` no solo puede ser el resultado de la resta entre dos objetos `date` o `datetime`, sino que también puede ser creado directamente, especificando un intervalo de tiempo usando diversos argumentos. Esto permite trabajar con intervalos de días, horas, semanas, entre otros, facilitando cálculos relacionados con el tiempo.

El constructor de `timedelta` acepta los siguientes argumentos opcionales:
- `days`: Número de días.
- `seconds`: Número de segundos.
- `microseconds`: Número de microsegundos.
- `milliseconds`: Número de milisegundos.
- `minutes`: Número de minutos.
- `hours`: Número de horas.
- `weeks`: Número de semanas.

Cada uno de estos argumentos puede ser positivo o negativo, y el valor predeterminado para todos ellos es 0. Los valores se almacenan internamente en días, segundos y microsegundos, realizando conversiones automáticas según sea necesario (por ejemplo, semanas a días, horas a segundos).

En el siguiente ejemplo, creamos un objeto `timedelta` sumando 2 semanas, 2 días y 3 horas:

```
from datetime import timedelta

# Crear un objeto timedelta con 2 semanas, 2 días y 3 horas
delta = timedelta(weeks=2, days=2, hours=3)
print(delta)
```

### Acceso a los atributos internos de `timedelta`

Internamente, los objetos `timedelta` almacenan el tiempo en días, segundos y microsegundos. Puedes acceder a estos valores directamente usando los atributos `.days`, `.seconds` y `.microseconds`.

En el siguiente ejemplo, desglosamos el objeto `timedelta`:

```
from datetime import timedelta

# Crear un objeto timedelta
delta = timedelta(weeks=2, days=2, hours=3)
print("Días:", delta.days)            # Devuelve 16 días
print("Segundos:", delta.seconds)      # Devuelve 10800 segundos (3 horas convertidas a segundos)
print("Microsegundos:", delta.microseconds)  # Devuelve 0
```

## Operaciones con `timedelta`

Podemos utilizar el objeto `timedelta` en conjunto con las clases `date` y `datetime` del módulo `datetime` para realizar operaciones como la multiplicación y la suma de intervalos de tiempo.

### Multiplicación de `timedelta`

El objeto `timedelta` puede multiplicarse por un número entero. Esta operación multiplica todos los componentes del intervalo de tiempo, como los días y las horas. Veamos un ejemplo:

```
from datetime import timedelta

# Crear un objeto timedelta con 16 días y 2 horas
delta = timedelta(weeks=2, days=2, hours=2)
print(delta)

# Multiplicar el timedelta por 2
delta2 = delta * 2
print(delta2)
```
En este caso, el objeto `delta` representa 16 días y 2 horas, y al multiplicarlo por 2, obtenemos un nuevo objeto `timedelta` que representa 32 días y 4 horas. Tanto los días como las horas se multiplican por 2.

### Suma de `timedelta` con objetos `date` y `datetime`

Otra operación útil es la suma de un objeto `timedelta` con un objeto `date` o `datetime`. Esto permite ajustar fechas o momentos en el tiempo añadiendo días, horas, minutos o semanas.

En el siguiente ejemplo, sumamos el objeto `timedelta` al objeto `date` y al objeto `datetime`:

```
from datetime import timedelta, date, datetime

# Crear un objeto timedelta
delta = timedelta(weeks=2, days=2, hours=2)

# Crear un objeto date y sumarle el timedelta
d = date(2019, 10, 4) + delta
print(d)

# Crear un objeto datetime y sumarle el timedelta
dt = datetime(2019, 10, 4, 14, 53) + delta
print(dt)
```

En el primer caso, la suma de `date(2019, 10, 4)` con el `timedelta` de 16 días y 2 horas nos da una nueva fecha: **2019-11-05**.

En el segundo caso, la suma del objeto `datetime(2019, 10, 4, 14, 53)` con el mismo `timedelta` nos da una nueva fecha y hora: **2019-11-05 18:53:00**.

## Cuestionario

1. ¿Cuál es el resultado del siguiente fragmento de código?
    ```
    from datetime import time

    t = time(14, 39)
    print(t.strftime("%H:%M:%S"))
    ```

2. ¿Cuál es el resultado del siguiente fragmento de código?
    ```
    from datetime import datetime

    dt1 = datetime(2020, 9, 29, 14, 41, 0)
    dt2 = datetime(2020, 9, 28, 14, 41, 0)

    print(dt1 - dt2)
    ```
## Solución cuestionario

1. Ejercicio 1

    `14:53:00`

2. Ejercicio 2

    `1 day, 0:00:00`