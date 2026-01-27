# Día 02 — Basic Commands & Scripting

## 🎯 Objetivos del día

1. Aprender los comandos básicos de Linux para moverse por el sistema  
2. Crear y ejecutar **scripts Bash**  
3. Manejar **variables y variables de entorno**  
4. Ejecutar procesos en **foreground y background**  
5. Usar **jobs**, `fg`, `bg` y matar procesos con `kill`  

---

## 🔹 Teoría resumida

### Comandos básicos de Linux

- `ls` → listar archivos y carpetas  
- `cd` → cambiar directorio  
- `pwd` → ver directorio actual  
- `mkdir` → crear directorio  
- `rm` → eliminar archivo o directorio  
- `cp` → copiar  
- `mv` → mover o renombrar  
- `cat` → mostrar contenido de un archivo  
- `echo` → mostrar texto o variables en terminal  

---

### Variables

- **Locales**: solo existen dentro del script o sesión actual

```bash
nombre="Matias"
echo $nombre

-**De entorno**: se exportan para otros scripts o subprocesos

```bash
export Curso=Linux
./otro_script.sh

Guardar variables de entorno de forma permanente:
agregar al ~/.bashrc

export Curso=Linux

Scripts Bash básicos
Crear script:
nano primerscript.sh

Contenido de ejemplo:
#!/bin/bash
clear
nombre="Matias"
echo "Hola, soy $nombre"
export nombre
echo "Voy a llamar a otro script"
sleep 2
./segundoscript.sh

Segundo script:
#!/bin/bash
clear
echo "El nombre del script anterior es: $nombre"

Hacer ejecutables los scripts:
chmod +x primerscript.sh segundoscript.sh

Ejecutar:
./primerscript.sh


Foreground / Background / Jobs

Ejecutar en foreground (terminal ocupada):
sleep 60

Ejecutar en background (terminal libre):
sleep 300 &

Listar jobs activos:
jobs

Traer job a foreground:
fg %1

Mandar job a background:
bg %1

Matar procesos:
ps aux | grep sleep
kill <PID>
kill -9 <PID>  # forzado

Comandos adicionales importantes
Información del sistema
uname -a
lsb_release -a
whoami
pwd

Manejo de procesos simples
ps
top
pgrep <nombre_proceso>
kill <PID>
killall <nombre_proceso>

Navegación y edición
nano <archivo>
tree
