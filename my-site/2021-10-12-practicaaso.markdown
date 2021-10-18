---
layout:     
title:  "Instalación de Debian 11 en el equipo de trabajo"
date:   2021-10-12 22:33:29 +0200
categories: jekyll update
---

***Parte editada por Davidrg para la tarea Prueba1***


# Instalación de Debian 11 en el equipo de trabajo
## Primeros pasos

En la siguiente tarea realizaremos una instalación de la última versión de Debian, la 11 (Bullseye), realizaremos la típica instalación, exceptuando los volúmenes lógicos, por lo que omitiremos los típicos pasos.

Debemos seguir la siguiente estructura de directorios, ya que deseamos configurar nuestra máquina linux como un servidor.
Disponemos de unos 250 GB por lo que realizaremos el reparto de espacio de la siguiente manera:

- / → 30GB
- /home → 100GB
- /var → 50GB
- /usr → 8GB
- /tmp → 2GB

Nos sobran unos 11 GB para repartir en un futuro en caso de necesitar más espacio.


##Configuración LVM

Una vez realizadas las distintas particiones pasaremos a la configuración de los volúmenes lógicos.

Debemos crear un grupo de volúmenes, posteriormente crearemos un volúmen lógico con el nombre de una partición, por ejemplo, creamos un volúmen lógico llamado home y a este le asignamos la partición de home. Debemos hacer esto con todas las particiones, es decir, con /, /home, /var, /usr y /tmp.

A la hora de seleccionar el entorno de escritorio debian, debemos seleccionar la opción "ssh_server", ya que lo utilizaremos bastante a la hora de acceder a otras máquinas.

Salida del comando lsblk una vez finalizada la instalación:
![Imagen](https://dit.gonzalonazareno.org/redmine/attachments/download/32599/lsblk.png)

## Drivers

Es muy probable que cuando terminemos la instalación de nuestro sistema, nos de algún problema relacionado con los drivers del equipo.
Para solucionar esto debemos introducir el siguiente comando:

`$ sudo -E hw-probe -all -upload`


Este comando nos mostrará un enlace que debemos escribir en la página "Linux Hardware" y nos mostrará los problemas relacionados con los drivers de nuestro equipo.
En mi caso, tuve problema con el driver del wi-fi, para solucionarlo descargue dicho driver que es el siguiente:
iwlwifi-2030-6.ucode
Una vez descargado lo copiamos en la carpeta /lib/firmware, posteriormente realizamos un update y un upgrade. Reiniciamos el equipo y ya se soluciona.
