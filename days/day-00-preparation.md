# Día 00 — Preparación del entorno

## Sistema
- Entorno: WSL2
- Distribución: Ubuntu 24.04.3 LTS (noble)
- Kernel: 6.6.x microsoft-standard-WSL2

---

## Usuario
- Usuario principal: matias
- Directorio home: /home/matias
- Acceso a sudo: sí

---

## Objetivo personal
Realizar el **Linux Upskill Challenge desde cero** para afianzar los
fundamentos de Linux, procesos, permisos, logs y scripting,
documentando todo el aprendizaje de forma ordenada y progresiva.

---

## ¿Qué es Linux?
Linux, técnicamente, **no es un sistema operativo completo**, sino el
**kernel** del sistema operativo.

Las distribuciones como Ubuntu, Debian o Fedora combinan:
- El **kernel Linux**
- Herramientas GNU
- Una shell (bash)
- Un gestor de paquetes

A este conjunto se lo conoce como **GNU/Linux**.

---

## ¿Qué es el Kernel?
El **kernel** es el núcleo del sistema operativo y se encarga de:

- Gestionar la CPU y los procesos
- Gestionar la memoria RAM
- Controlar el hardware y los drivers
- Gestionar discos y sistemas de archivos
- Aplicar permisos y seguridad

El usuario **no interactúa directamente con el kernel**, sino a través
de la shell y los comandos.

### Esquema simplificado
Usuario
↓
Shell (bash)
↓
Comandos (ls, cd, apt…)
↓
Kernel
↓
Hardware

---

## Información del kernel y del sistema

### Ver la versión del kernel
```bash
uname -r

Ver información completa del sistema
uname -a

Ver información de la distribución
cat /etc/os-release


Nota importante:
uname muestra información del kernel
/etc/os-release identifica la distribución

¿Qué es la shell?

La shell es el intérprete de comandos que permite al usuario
interactuar con el sistema.

La shell más común es bash.

Ver qué shell está en uso
echo $SHELL

Usuarios en Linux

Linux distingue entre:

Usuario normal → trabajo diario

Usuario root → control total del sistema

Buenas prácticas:

No trabajar como root

Usar sudo solo cuando sea necesario

Ver el usuario actual
whoami

Sistema de archivos

Linux utiliza un único árbol de directorios, cuyo punto de inicio es:

/


No existen unidades como C: o D:.
Todo el sistema de archivos parte del directorio raíz /.

Comandos básicos del Día 00
Mostrar el directorio actual
pwd

Listar archivos
ls
ls -l
ls -a


-l muestra permisos y detalles

-a incluye archivos ocultos

Ver el nombre del equipo
hostname

Verificar acceso a sudo
sudo -v

Notas del entorno

El comando tree no venía instalado por defecto

Se instaló utilizando:

sudo apt install tree

Conceptos clave (LPI Essentials)

Linux es el kernel

El kernel gestiona hardware y recursos

El usuario no interactúa directamente con el kernel

La shell es el intermediario

Todo el sistema de archivos comienza en /

uname → kernel

/etc/os-release → distribución
