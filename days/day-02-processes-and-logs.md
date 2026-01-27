
# Día 02 — Procesos y Logs

## Foreground / Background / Jobs / PID

- **Foreground:** terminal ocupada hasta que el proceso termine  
  - Ejemplo: `sleep 60`
  - Aplicación práctica: lo ejecutaste y la terminal quedó ocupada hasta que terminó.

- **Background:** terminal libre, proceso sigue corriendo  
  - Ejemplo: `sleep 120 &`
  - Aplicación práctica: lo ejecutaste y la terminal quedó libre inmediatamente.

- **Jobs:** comandos gestionados por Bash (%1, %2, etc.)  
  - `jobs` → lista jobs de la terminal actual  
  - **`fg %1`** → trae un job detenido o en background a foreground  
    - Aplicación práctica: ejecutaste `sleep 120 &` y luego `fg %1` para traerlo a primer plano.
  - **`bg %1`** → manda un job detenido a background  
    - Aplicación práctica: si pausaste un job con `Ctrl+Z`, `bg %1` lo puso en background.
  - **Nota:** si el proceso termina, `%1` desaparece → `bg %1` devuelve `no such job`.

- **PID:** ID real del proceso en el sistema  
  - `ps aux | grep <comando>`  
  - `pgrep <comando>`  
  - `kill <PID>` → termina proceso, funciona desde cualquier terminal  

**Reglas clave:**
1. `%<job>` solo existe mientras Bash tiene el job registrado  
2. Cuando un job termina, desaparece → `bg %1` falla  
3. PID existe hasta que el proceso termina  

---

## Listado de procesos

- `ps aux` → lista todos los procesos  
- `ps -u matias` → procesos del usuario matias  
- `pgrep sleep` → busca PID de procesos sleep  
- Observaciones:
  - PID, usuario, %CPU, %MEM, estado (S=sleep, R=running)
  - Foreground / Background se refleja en jobs

---

## Matar procesos

- `kill <PID>` → normal (TERM)  
- `kill -9 <PID>` → forzado (SIGKILL)  
- No podés matar procesos de otros usuarios sin `sudo`  

---

## Logs

- `/var/log/syslog` → log principal del sistema  
- Últimas líneas:

```bash
tail -n 20 /var/log/syslog

Seguir en tiempo real:

sudo tail -f /var/log/syslog


Explorar paginado:

less /var/log/syslog
