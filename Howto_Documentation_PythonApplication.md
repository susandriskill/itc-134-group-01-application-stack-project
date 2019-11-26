
# Create a Project
-----------------------------------------------------------

## Make a Directory for Project
**`mkdir` creates a directory following the path and name given in the next spaces and `&& cd` also changes the directory to that one**
```Shell Session
$ sudo mkdir ~/projectname && cd ~/projectname
```
## Create Django Project
**It's important that you know where your Django files are so you can point the system to the django-admin.py file and the `startproject` module**
**In our case, the django-admin.py file was located in: /usr/local/lib/python3.7/dist-packages/django/bin/django-admin.py **
```Shell Session
~/projectname$ sudo python3 /PATH_TO_DJANGO/BIN/DJANGO-ADMIN.PY startproject project_name
```

## Allowing Outside IPs
**If you are setting up your server on a cloud server with a different IP than your computer, you will need to complete this step to be able to access the site before it goes live.**
``Shell Session
~/projectname/project_name$ sudo nano settings.py
```
Inside `settings.py` add your external IP address to the list of `ALLOWED_HOSTS = ['YOUR.IP.HERE']
Save and close settings.py and then check your server (you need to be on the same level as your manage.py file):

## Check Django
```Shell Session
~/projectname/project_name$ sudo python3 manage.py runserver 0.0.0.0:8000
Watching for file changes with StatReloader
Performing system checks...
System check identified no issues (0 silenced).
You have 17 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): a
dmin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```

Your server is now running and should be updating with any traffic. If you navigate to `http://SERVERIP:80/` you should see the Django framework.
To exit your server hit _CTRL+'D'_

## Create First App
```Shell Session
~/projectname/project_name/$ sudo python3 manage.py startapp helloworld
~/projectname/project_name/$ cd helloworld
~/projectname/project_name/$ sudo nano views.py
```

In views.py, add the following:

```python

from django.shortcuts import render
from django.http import HttpResponse

def home(request):
	return HttpResponse('<h1> Hello World </h1>')
```

Save and close.
Open urls.py in your helloworld directory and add the following code:
```python
from django.urls import path
from . import views

urlpatterns = [
        path('', views.home, name='hello-world'),
```

Save and close.
Next, open up the project_name project file and edit urls.py:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('helloworld/', include('helloworld.urls')),
]
```
Save and Close.

## Check Your App
```Shell Session
$ sudo python3 manage.py runserver
```

Navigate to `http://SERVERIP:80`.
You should get an error that lists acceptable paths.
Navigate to the suggested `http://SERVERIP:80/helloworld

**Hello World** should be printed on your screen. Your app is successfully working and outputing HTML via Python.

