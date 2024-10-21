# Instalación de pip

## Instalación de pip en Windows

El instalador de Python para MS Windows ya contiene pip, por lo que no es necesario seguir ningún otro paso para instalarlo. 
Podemos verificar si pip ya está instalado, ejecutando en la consola el siguiente comando:

```
pip --version
```

Si pip está instalado correctamente, verás un mensaje con la versión instalada, algo como: `pip 21.2.4 from ... (python 3.x)`.

La ausencia de este mensaje puede significar que la variable `PATH` apunta incorrectamente a la ubicación de los binarios de Python o no apunta a ellos en absoluto. La forma más fácil de reconfigurar la variable `PATH` es reinstalar Python, indicando al instalador que lo configure por ti.

## Instalación de pip en Linux

En **Linux**, la instalación de **pip** puede variar según la distribución que estés utilizando. Lo primero, vamos a verificar la instalación de pip, para ello ejecuta en el terminal:

```
pip --version
```

Recuerda que si tienes instalado Python2 en tu sistema, puede que si ejecutamos `pip` corresponda al instalador de paquetes de Python2. Si la salida del comando te indica que está utilizando Python2, entonces debes usar el comando `pip3`.

Si no tienes instalado pip, según la distribución tendrás que instalar el paquete correspondiente. Por ejemplo, si estás trabajando con Debian/Ubuntu:

```
sudo apt update
sudo apt install python3-pip
```

Si usas otras distribuciones tendrás que instalar el paquete `python3-pip` con el gestor de paquetes de la distribución.

## Instalación de pip en MacOS

Si eres un usuario de Mac y has instalado Python 3 usando el instalador brew, pip ya está presente en tu sistema y listo para funcionar. Compruébelo con la siguiente instrucción:

```
pip3 --version
``
