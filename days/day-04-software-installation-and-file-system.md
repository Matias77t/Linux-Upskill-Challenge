# Día 04 – Instalación de software y exploración del sistema de archivos

## Objetivos
- Aprender a instalar software usando `apt`
- Comprender la jerarquía de directorios de Linux
- Leer archivos importantes del sistema y logs básicos

---

## Ejercicio 1 – Actualizar e investigar paquetes

```bash
sudo apt update
sudo apt search mc

Pregunta:
¿Qué hace cada comando y por qué deben ejecutarse en este orden?

Respuesta y razonamiento:

apt update actualiza el índice de paquetes desde los repositorios.

apt search mc busca paquetes relacionados con “mc”.

Es importante ejecutar primero update para trabajar con información actualizada

Ejercicio 2 – Instalación de software

sudo apt install mc

Pregunta:
¿Qué ocurre y dónde se instala el software?

Respuesta y razonamiento:

Se instala Midnight Commander desde los repositorios.

Los binarios suelen instalarse en /usr/bin.

Los archivos de configuración, si existen, van en /etc.

Los datos compartidos suelen estar en /usr/share.

Ejercicio 3 – Exploración del sistema de archivos

mc

Pregunta:
¿Qué es este programa y por qué es útil?

Respuesta y razonamiento:

mc es un gestor de archivos en modo texto.

Facilita la navegación por el sistema y la comprensión de la estructura de directorios.

Ejercicio 4 – Usuarios del sistema

head -n 5 /etc/passwd


Pregunta:
¿Qué representa el archivo /etc/passwd?

Respuesta y razonamiento:

Contiene información básica de las cuentas de usuario.

Cada línea representa un usuario con su UID, directorio home y shell.

Ejercicio 5 – Logs de autenticación

tail -n 10 /var/log/auth.log

Pregunta:
¿Por qué este archivo es importante?

Respuesta y razonamiento:

Registra eventos de autenticación (sudo, SSH, inicios de sesión).

Es clave para auditoría de seguridad y diagnóstico de problemas.

Pregunta tipo examen (LPI)

Si un programa está instalado pero no se puede ejecutar escribiendo su nombre, ¿qué puede estar fallando?

Respuesta y razonamiento:

El binario no está en una ruta incluida en la variable $PATH.

O el paquete no instaló un ejecutable accesible para el usuario.
