# Step3 - Permissions

**Django permissions** = Django comes with a simple permissions system. It provides a way to assign permissions to specific users and groups of users.

First make sure that 'rest_framework' was properly installed in your django app.

Activate virtual environment.

```
pipenv shell
```

1. Update your `tutorial/api/urls.py` with the following.
```
urlpatterns = [
    ...
    path('api-auth', include('rest_framework.urls'))
]
```

2. Create superuser account.

```
python3 manage.py createsuperuser --email admin@example.com --username admin
```
after that it will ask to enter password.

3. Start django server.

```
python3 manage.py runserver
```
it will serve `http://127.0.0.1:8000/`

4. Click `login` and enter your credentials.

### Permissions

There are two common permissions that you can use in django rest framworks these are by `Individual views` or by `Global settings`

Update `tutorial/languages/views.py` and import **permissions** and below `LanguageView` class add **permission_classes = (permissions.IsAuthenticatedOrReadOnly,)**

```
# tutorial/languages/views.py
from django.shortcuts import render
from rest_framework import viewsets, permissions
from .models import Language, Paradigm, Programmer
from .serializers import LanguageSerializer, ParadigmSerializer, ProgrammerSerializer

class LanguageView(viewsets.ModelViewSet):
    queryset = Language.objects.all()
    serializer_class = LanguageSerializer
    permission_classes = (permissions.IsAuthenticatedOrReadOnly,)

class ParadigmView(viewsets.ModelViewSet):
    queryset = Paradigm.objects.all()
    serializer_class = ParadigmSerializer

class ProgrammerView(viewsets.ModelViewSet):
    queryset = Programmer.objects.all()
    serializer_class = ProgrammerSerializer
```

Example of Django permissions.

1. **IsAuthenticatedOrReadOnly** = Can view rest api even NOT AUTHENTICATED Can view form if AUTHENTICATED

2. **IsAuthenticated** = Can view both rest api and form if AUTHENTICATED

Basic syntax : `permission_classes = (permissions.IsAuthenticatedOrReadOnly,)`.

You can also set `global` permissions under `tutorial/api/settings.py` like example below.

```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': (
        'rest_framework.permissions.IsAuthenticatedOrReadOnly',
    )
}
```

Complete permissions documentation: https://www.django-rest-framework.org/api-guide/permissions/
