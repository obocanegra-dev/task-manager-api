# Task Manager API

Una API RESTful para gestión de tareas desarrollada con Python, Flask y SQLAlchemy.

## Requisitos

- Python 3.9+
- pip

## Instalación

1. Clonar repositorio:
```bash
git clone https://github.com/obocanegra-dev/task-manager-api.git
cd task-manager-api
```

2. Crear y activar entorno virtual:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate    # Windows
```

3. Instalar dependencias:
```bash
pip install -r requirements.txt
```

4. Inicializar base de datos:
```bash
flask shell
>>> from app import db
>>> db.create_all()
>>> exit()
```

## Uso

Iniciar servidor:
```bash
python app.py
```

### Endpoints

- `POST /tasks`: Crear nueva tarea
  ```bash
  curl -X POST http://localhost:5000/tasks -H "Content-Type: application/json" -d '{"title": "Mi primera tarea", "description": "Esta es una descripción"}'
  ```

- `GET /tasks`: Obtener todas las tareas
  ```bash
  curl http://localhost:5000/tasks
  ```

- `GET /tasks/<id>`: Obtener una tarea específica
  ```bash
  curl http://localhost:5000/tasks/1
  ```

- `PUT /tasks/<id>`: Actualizar tarea
  ```bash
  curl -X PUT http://localhost:5000/tasks/1 -H "Content-Type: application/json" -d '{"title": "Título actualizado"}'
  ```

- `DELETE /tasks/<id>`: Eliminar tarea
  ```bash
  curl -X DELETE http://localhost:5000/tasks/1
  ```

## Estructura de una tarea
```json
{
    "id": 1,
    "title": "Título de tarea",
    "description": "Descripción de la tarea",
    "created_at": "2023-08-01T12:00:00"
}
```

## Posibles Mejoras
- Añadir autenticación de usuarios
- Permitir marcar tareas como completadas
- Filtrar tareas por estado
- Añadir fechas límite y prioridades
```
