
# Django
### passo a passo para criar um novo projeto com painel admin e superusuario

comandos para criar painel admin com Django

## Inicar projeto e executar servidor
Criar venv
```
python3 -m venv .venv
```

Acessar venv
```
source .venv/bin/activate
```
Instalar Django
```
pip install django
```


Iniciar Projeto

```
django-admin startproject Nome-do-projeto
```

Executar o servidor:

```
python3 manage.py runserver
```

### Executar as migrations internas do Django

```
python3 manage.py makemigrations
```

```
python3 manage.py migrate
```

### Crie uma nova aplicação

Comando para criar Aplicação

```
django-admin startapp nome-aplicacao
```

Adionar a aplicação ao `INSTALLED_APPS` do arquivo `settings.py`

```
 "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "nome-aplicacao",
```

### Criar nova Tabela

Criar uma nova classe com o bome da Tabela no arquivo `models.py`

Exemplo tasks
```
from django.db import models

class Task(models.Model):
    title = models.CharField(max_length=200)
    description = models.TextField()
    due_date = models.DateField()
    completed = models.BooleanField(default=False)
    priority = models.IntegerField(choices=((1, 'Baixa'), (2, 'Média'), (3, 'Alta')))
    created_at = models.DateTimeField(auto_now_add=True)
```

### Executar as migrations internas do Django

```
python3 manage.py makemigrations
```

```
python3 manage.py migrate
```

### Criação de um novo superusuário / Django Admin

```
python manage.py createsuperuser
```

forneça um nome de usuário, um e-mail e uma senha quando solicitado no terminal.


registre o modelo no arquivo `admin.py`

exemplo tasks
```
from django.contrib import admin
from .models import Task


admin.site.register(Task)
```


executar o servidor local
```
python manage.py runserver
```


## Referências
[Documentação oficial](https://docs.djangoproject.com/en/4.2/)

[Configurações de Database](https://docs.djangoproject.com/en/3.2/ref/settings/#databases)


[Migrations](https://docs.djangoproject.com/en/3.2/topics/migrations/)

[Recursos integrados de segurança](https://docs.djangoproject.com/en/4.2/topics/security/)
