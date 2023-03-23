### Project structure

```markdown
minidjango_ver1
├── app1     (django application)
│   ├── __init__.py
│   ├── admin.py   (built in django-admin GUI)
│   ├── apps.py    (application configuration)
│   ├── migrations  (keeping track of DB changes)
│   │   └── __init__.py
│   ├── models.py  (To define DB)
│   ├── tests.py   (To define unit-test)
│   └── views.py   (Contains business logic)
├── manage.py
├── minidjango_ver1   (django project setting directory)
│   ├── __init__.py
│   ├── asgi.py      (project instantiation)
│   ├── settings.py  (project configuration)
│   ├── urls.py      (url configuration)
│   └── wsgi.py      (project instantiation)
```

### STEPs

1. create `venv`
2. activate `venv`
3. `pip install django`
4. `django-admin`  (CLI tool options - `django-admin --help`)
5. `django-admin startproject <project-name>`


#### Skeleton of project structure because of `django-admin startproject` command

```markdown

randomproject    # <-- (django project root)
├── manage.py    # <-- (entrypoint of django project)
└── randomproject   # <-- (django project setting package)
    ├── __init__.py
    ├── asgi.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

### Easier steps to get started with `Django`

1. Install django globally (system-wide installation `pip install django`) 
2. `django-admin startproject minidjango_ver1`
3. Open the project `minidjango_ver1` in Pycharm
4. Create a `venv` under project root (`minidjango_ver1`)
5. Active `venv` and `pip install django`
6. Write down project structure manually 

```markdown

minidjango_ver1  (django project root)
    - manage.py 
    - minidjango_ver1  (django project setting directory)
         - __init__.py
         - wsgi.py
         - settings.py
         - urls.py

```
7. Navigate to django project root (where `manage.py` file exists)
8. `python manage.py startapp app1`  (`django-admin startapp app1`)
9. Write down project structure manually 
10. Register newly created application in `settings.py`. 
    To register add application name to the existing list called `INSTALLED_APPS`
11. Write a first `hello_world` view inside `minidjango_ver1/app1/views.py`
```python
from django.http import HttpResponse


def home(request):
    return HttpResponse('Hello, World!')
```
12. Do URL-binding in project urls.py file (`minidjango_ver1/minidjango_ver1/urls.py`)
```python
from django.contrib import admin
from django.urls import path
from app1 import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('app1/', views.home, name='home')
]
```
13. Run project with command `python manage.py runserver`
14. Open browser `http://127.0.0.1:8000/app1`





### when you install django

- you get `django-admin` CLI tool
- you get `sqlite3` database
- you get `development server`