# Cómo usar pip

## Dependencias

Cuando creas una aplicación en Python que usa varios paquetes, esos paquetes pueden tener sus propias dependencias. Por ejemplo, si tu aplicación usa un paquete llamado `nyse`, y este a su vez depende de otros como `wallstreet` y `bull`, esos paquetes también deben ser instalados para que tu aplicación funcione correctamente. Esto es lo que se llama una **dependencia**: un software que necesita otro software para funcionar.

El problema surge cuando un usuario necesita instalar todos los paquetes y sus dependencias manualmente, lo que se conoce como el **infierno de dependencias**. Sin embargo, **pip** resuelve este problema automáticamente. Pip puede identificar y gestionar todas las dependencias necesarias, asegurando que todos los paquetes requeridos se descarguen e instalen correctamente, evitando la necesidad de hacerlo manualmente.

## Introducción a uso de pip

Lo primero que vamos a hacer es comprobar las opciones que nos ofrece esta herramienta, para ello ejecutamos:

```
pip help

Usage:   
  pip <command> [options]

Commands:
  install                     Install packages.
  download                    Download packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  inspect                     Inspect the python environment.
  list                        List installed packages.
  show                        Show information about installed packages.
  check                       Verify installed packages have compatible dependencies.
  config                      Manage local and global configuration.
  search                      Search PyPI for packages.
  cache                       Inspect and manage pip's wheel cache.
  index                       Inspect information available from package indexes.
  wheel                       Build wheels from your requirements.
  hash                        Compute hashes of package archives.
  completion                  A helper command used for command completion.
  debug                       Show information useful for debugging.
  help                        Show help for commands.
...
```
Si deseas saber más sobre cualquiera de las operaciones enumeradas, puedes utilizar la siguiente forma de invocación de pip:

```
pip help (operación o comando)
```

## Modos de funcionamiento de pip

pip puede trabajar en dos modos:

* **Privilegiado**: Es el modo por defecto, los paquetes python que gestionamos están accesible para todos los usuarios del sistema. 
* **A nivel de usuario**: Los paquetes que gestionamos sólo serán accesibles desde el usuario con el que estamos trabajando. Para usar este modo tendremos que indicar la opción `--user`.

Algunos sistemas operativos más modernos muestran un mensaje de aviso, indicando que instalar paquetes Python con pip puede causar problemas en la integridad de los paquetes python que existen en el sistema, o los que podemos instalar directamente desde los paquetes de la distribución, ya que se pueden romper las dependencias.

Para solucionar este problema, lo más recomendable es el uso de entornos virtuales. Sin embargo en este curso, vamos a a gestionar los paquetes con un usuario sin privilegio y si nos aparece el mensaje de advertencia, indicaremos el parámetro `--break-system-packages` para que nos permita que pip gestione paquetes.

## Buscando paquetes en PyPi

Aunque el comando `pip` nos ofrece una opción de búsqueda de paquetes (`search`) en versiones más modernas de Python ha sido deshabilitada por problemas de rendimiento. Lo más fácil para buscar información sobre los paquetes que podemos instalar es buscarlos directamente desde la página web del repositorio oficial PyPi: [https://pypi.org/search](https://pypi.org/search).

## Principales funcionalidades de pip

Aquí tienes un resumen de las principales funciones de `pip`, la herramienta de gestión de paquetes para Python:

* **`pip list`**: Muestra una lista de los paquetes de Python instalados en tu entorno. Puedes usar opciones como `--user` para ver solo los paquetes instalados para el usuario.
* **`pip show <paquete>`**: Muestra información detallada sobre un paquete instalado. Proporciona detalles sobre la versión del paquete, la ruta de instalación, las dependencias, la licencia, etc.
* **`pip install <paquete>`**: Instala un paquete de Python desde el repositorio PyPI. Con la opción `--user` sólo es accesible desde el usuario sin privilegios con el que estamos trabajando. También puedes especificar una versión en particular con `==`.
* **`pip install -U <paquete>`**: Actualiza un paquete instalado a la versión más reciente. Si el paquete ya está instalado, la opción `-U` (o `--upgrade`) lo actualizará a la última versión disponible en PyPI.
* **`pip uninstall <paquete>`**: Desinstala un paquete instalado. No hace falta indicar `--user` se intentará eliminar el paquete en cualquiera de los modos que se ha instalado.