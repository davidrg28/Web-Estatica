# Web-Estatica
Implantación y despliegue de una aplicación web estática 

1. Selecciona una combinación entre generador de páginas estáticas y servicio donde desplegar la página web. Escribe tu propuesta en redmine, cada propuesta debe ser original.
Jekyll y Neocities

2. Comenta la instalación del generador de página estática. Recuerda que el generador tienes que instalarlo en tu entorno de desarrollo. Indica el lenguaje en el que está desarrollado y el sistema de plantillas que utiliza.

Jekyll requiere el entorno de trabajo de Ruby ya que este incluye ciertas librerías necesarias para su uso. Necesitamos instalar el paquete build-essential:
$ sudo apt -y install make build-essential

También instalamos la paquetería relacionada con ruby:
$ sudo apt -y install ruby ruby-dev

Necesitamos exportar un par de variables gem que nos servirán para usar jekyll. Añadimos las siguientes líneas al fichero ~/.bashrc:
export GEM_HOME=$HOME/gems
export PATH=$HOME/gems/bin:$PATH

Para efectuar los cambios:
$ source ~/.bashrc

Una vez hecho esto, usaremos gem para instalar Jekyll y Bundler que nos solucionará algunas dependencias.

$ gem install bundler
$ gem install jekyll

3. Configura el generador para cambiar el nombre de tu página, el tema o estilo de la página,… Indica cualquier otro cambio de configuración que hayas realizado.


4. Genera un sitio web estático con al menos 3 páginas. Deben estar escritas en Markdown y deben tener los siguientes elementos HTML: títulos, listas, párrafos, enlaces e imágenes. El código que estas desarrollando, configuración del generado, páginas en markdown,… debe estar en un repositorio Git (no es necesario que el código generado se guarde en el repositorio, evítalo usando el fichero .gitignore).


5. Explica el proceso de despliegue utilizado por el servicio de hosting que vas a utilizar.


6. Piensa algún método (script, scp, rsync, git,…) que te permita automatizar la generación de la página (integración continua) y el despliegue automático de la página en el entorno de producción, después de realizar un cambio de la página en el entorno de desarrollo. Muestra al profesor un ejemplo de como al modificar la página se realiza la puesta en producción de forma automática.
