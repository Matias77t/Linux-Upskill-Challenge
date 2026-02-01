# Día 01 — Conocer el sistema (Get to know your server)

## Objetivo
Familiarizarse con el sistema Linux en uso, identificando:
- quién es el usuario
- qué sistema operativo y kernel están corriendo
- el estado general del sistema
- recursos disponibles (CPU, memoria, disco)
- usuarios y procesos activos

Este día busca **entender el entorno antes de administrarlo**.

---

## Usuario y host

### Usuario actual
```bash
whoami
Usuario: matias

Nombre del equipo
hostname

Hostname: Matt77

Información del sistema
Kernel y arquitectura
uname -a

Permite conocer:

versión del kernel

arquitectura

nombre del host

Distribución Linux
cat /etc/os-release

Tiempo activo y carga del sistema
Tiempo encendido y carga
uptime

Tiempo activo: 3h 21m

Load average: 0.05 0.03 0.01

Interpretación:

La carga es muy baja

El sistema está sin estrés

Usuarios conectados
Ver usuarios activos
w

Alternativa
who

Observaciones:

No hay otros usuarios conectados

El sistema está siendo usado solo por el usuario principal

Procesos en ejecución
Vista en tiempo real
top

Permite observar:

uso de CPU

uso de memoria

procesos activos

Listado completo de procesos
ps aux

Observaciones:

Bash en foreground

Procesos propios del sistema

No se detectan procesos anómalos

Memoria RAM
Uso de memoria
free -h

Memoria total: 8G

Memoria disponible: 3.8G

Razonamiento:

Linux usa memoria como caché

Memoria “usada” no implica problema si hay disponible

Espacio en disco
Uso de disco
df -h

Disco total: 256G

Espacio disponible: 120G

Interpretación:

Hay suficiente espacio libre

No hay riesgo inmediato de saturación

Exploración inicial del sistema de archivos
Ver directorios principales
ls /

Permite identificar:

/etc → configuración

/var → logs y datos variables

/home → usuarios

/usr → programas

/bin y /sbin → comandos esenciales

Comandos clave del Día 01:

whoami → usuario actual
hostname → nombre del equipo
uname → información del kernel
uptime → tiempo activo y carga
w, who → usuarios conectados
top, ps aux → procesos
free -h → memoria
df -h → disco
ls / → estructura del sistema
