# Movies 0.1v  
list movies on the engine Django 3.1.14
```
asgiref==3.5.0
Django==3.1.14
Pillow==9.0.1
pytz==2022.1
sqlparse==0.4.2
db.sqlite3
```  

## 0 - создание среды
```
python3.8 -m venv venv
source venv/bin/activate  # вход в среду
deactivate  # выход в среду выше
```

## 1 - утанавливать в активированной среде
```
pip install django==3.1.14
pip freeze   # Команда pip freeze выводит все установленные в интерпретатор сторонние пакеты.
``` 

## 2 - проект делаем
```
django-admin startproject config  # команда которая создает проект, (config - название проекта)
``` 

## 3 - создание приложения в проекте
```
python manage.py startapp movies
python manage.py runserver 5000
python manage.py migrate
```

## 4 - создание супер пользователя
```
$ python manage.py createsuperuser. Введите имя пользователя и нажмите Enter.
Username: admin. Теперь введите email:
Email address: admin@example.com. И наконец введите пароль. 
Password: ********** Password (again): ********* Superuser created successfully.
```

## 5 /movies/models.py добавить модель и осуществить миграцию
```
./manage.py makemigrations   # создаем миграцию
./manage.py migrate	         # Осуществляем миграцию
./manage.py shell            # можно войти в Django и покодить
p = Post(title='New post', slug='new-slug', body='new post body')
p.save()
pl = Post.objects.create(title='new post2', slug='new-slug-2', body='new 2 post body')
Post.objects.all()    # выводит всех
post = Post.objects.get(slug='new-slug')
post
post = Post.objects.get(slug__iexact='New-slug')    # регистро-независимые
post = Post.objects.filter(slug__contains='New')   # получить несколько
```