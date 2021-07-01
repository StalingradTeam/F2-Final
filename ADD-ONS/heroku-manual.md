# Heroku

 -чтобы сделать деплой на heroku необходимо:
            (при Debug=False)

 -перейти в каталог с проектом (например):
        cd C:\my_site

 -если используются статические файлы, то обязательно в проекте должны быть созданы две папки: static и staticfiles

  -выполняем следующие команды:

        git init
        git add .
        git commit -m "initial commit"
        heroku login
        heroku create
        heroku rename -a oldname newname (переименование приложения, если требуется)
        heroku addons:create heroku-postgresql --as DATABASE
        heroku config:set SECRET_KEY=Ваш_секретный_код
        git push heroku master
        heroku run python manage.py makemigrations
        heroku run python manage.py migrate
        heroku run python manage.py loaddata data.xml
        heroku run python manage.py createsuperuser


 -запустить приложение:
 
        heroku open

-перезапустить приложение:

        heroku restart

-обновить до новой версии:

        heroku update

-необходимо добавить в settings.py:

        import django_heroku                (в самый верх)
        django_heroku.settings(locals())    (в самый низ)

ALLOWED_HOSTS = []  (не надо в скобки ничего вписывать!)

- не забываем прятать SECRET_KEY

- в requirements.txt - добавить:

       django-heroku
       
- не забываем про Procfile:

       release: python manage.py migrate
       web: python manage.py runserver 0.0.0.0:$PORT
