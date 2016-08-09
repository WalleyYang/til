### Create Django project
$ django-admin startproject ProjectName

### Running the project
$ python manage.py runserver

### Create app inside project
$ python manage.py startapp app_name

### Templates
```
# Register app in settings.py
# Add index.html to templates directory
# Delete HttpResponse from views.py to render HTML template.

from django.shortcuts import render

def index(request):
	return render(request, ‘index.html’)
```
