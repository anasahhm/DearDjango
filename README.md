# Logoshelf
 
A web application built with Django that lets users track topics they're learning about and make journal entries as they learn. Each user has a private log — only they can see and manage their own topics and entries.
 
---
 
## Features
 
- User registration, login, and logout
- Create and manage personal learning topics
- Add, edit, and view journal entries per topic
- Access control — users can only see their own data
- Bootstrap-styled responsive UI
- Deployed on Heroku with PostgreSQL
 
---
 
## Tech Stack
 
- **Backend:** Python 3, Django
- **Frontend:** Bootstrap 3 (via django-bootstrap3)
- **Database:** SQLite (local) / PostgreSQL (production)
- **Deployment:** Heroku + Gunicorn
 
---
 
## Getting Started (Local Setup)
 
### 1. Clone the repository
 
```bash
git clone https://github.com/anasahhm/logoshelf.git
cd logoshelf
```
 
### 2. Create and activate a virtual environment
 
```bash
python -m venv ll_env
 
# macOS/Linux
source ll_env/bin/activate
 
# Windows
ll_env\Scripts\activate
```
 
### 3. Install dependencies
 
```bash
pip install -r requirements.txt
```
 
### 4. Apply migrations
 
```bash
python manage.py migrate
```
 
### 5. Create a superuser (optional, for admin access)
 
```bash
python manage.py createsuperuser
```
 
### 6. Run the development server
 
```bash
python manage.py runserver
```
 
Visit `http://localhost:8000/` in your browser.
 
---
## Models
 
### `Topic`
| Field | Type | Description |
|-------|------|-------------|
| `text` | CharField (max 200) | Topic name |
| `date_added` | DateTimeField | Auto-set on creation |
| `owner` | ForeignKey → User | The user who owns this topic |
 
### `Entry`
| Field | Type | Description |
|-------|------|-------------|
| `topic` | ForeignKey → Topic | Associated topic |
| `text` | TextField | Entry content |
| `date_added` | DateTimeField | Auto-set on creation |
 
