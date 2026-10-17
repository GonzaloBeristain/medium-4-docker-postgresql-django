# API de tareas

API REST construida con Django REST Framework y PostgreSQL.

## Configuración

1. Copia `.env.example` como `.env` y define las credenciales de PostgreSQL.
2. Crea la base de datos `tasks_db` (o usa el nombre indicado en `POSTGRES_DB`).
3. Ejecuta las migraciones y el servidor:

```powershell
.\venv\Scripts\python.exe manage.py migrate
.\venv\Scripts\python.exe manage.py runserver
```

La API queda disponible en `http://127.0.0.1:8000`.

### Con Docker

Si prefieres levantar la API junto a PostgreSQL en contenedores, copia `.env.example` como `.env` y ejecuta:

```powershell
docker compose up --build
```

El servicio de API aplica las migraciones automáticamente y queda expuesto en el puerto `8000`.

## Endpoints

| Método | Ruta | Acción |
| --- | --- | --- |
| GET, POST | `/api/tasks/` | Lista o crea tareas |
| GET, PUT, PATCH, DELETE | `/api/tasks/{id}/` | Consulta, actualiza o elimina una tarea |
| GET | `/api/health/` | Verifica el estado de la API |

Ejemplo de creación:

```json
{
  "title": "Preparar frontend",
  "description": "Conectar la lista a la API",
  "completed": false
}
```
