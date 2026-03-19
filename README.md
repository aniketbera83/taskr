# Taskr — Django Task Manager

A full-stack task manager with a Django REST API backend and a sleek dark-theme frontend.

## Features
- **Kanban board** — drag tasks across To Do / In Progress / Done columns
- **Categories** with custom colors
- **Priority levels** — Urgent, High, Medium, Low
- **Due dates** with overdue detection
- **Search & filter** by status, priority, category
- **REST API** — fully browsable at `/api/`
- **Django Admin** at `/admin/`

## Stack
- **Backend**: Django 4.2 + Django REST Framework + django-cors-headers
- **Database**: SQLite (zero config)
- **Frontend**: Vanilla JS + CSS served by Django templates

## Setup

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run migrations
python manage.py migrate

# 3. (Optional) Create admin user
python manage.py createsuperuser

# 4. (Optional) Load sample data
python manage.py loaddata sample_data.json

# 5. Start server
python manage.py runserver
```

Open http://localhost:8000

## API Endpoints

| Method | URL | Description |
|--------|-----|-------------|
| GET | `/api/tasks/` | List all tasks |
| POST | `/api/tasks/` | Create task |
| GET | `/api/tasks/{id}/` | Get task |
| PUT | `/api/tasks/{id}/` | Update task |
| PATCH | `/api/tasks/{id}/` | Partial update |
| DELETE | `/api/tasks/{id}/` | Delete task |
| PATCH | `/api/tasks/{id}/move/` | Move to status |
| GET | `/api/tasks/stats/` | Task statistics |
| GET | `/api/categories/` | List categories |
| POST | `/api/categories/` | Create category |
| PUT | `/api/categories/{id}/` | Update category |
| DELETE | `/api/categories/{id}/` | Delete category |

## Query Parameters (tasks list)
- `?status=todo|in_progress|done`
- `?priority=low|medium|high|urgent`
- `?category={id}`
- `?search={query}`

## Project Structure
```
taskmanager/
├── manage.py
├── requirements.txt
├── taskmanager/
│   ├── settings.py
│   └── urls.py
├── tasks/
│   ├── models.py       # Task + Category models
│   ├── serializers.py  # DRF serializers
│   ├── views.py        # ViewSets
│   ├── urls.py         # Router
│   └── admin.py
├── templates/
│   └── index.html      # Single-page app
└── static/
    ├── css/main.css
    └── js/app.js
```
