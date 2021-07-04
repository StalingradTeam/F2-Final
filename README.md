# F2-Final

Веб-приложение: Опросы

В работе задействованы Django и PostgreSQL.

Веб-приложение запущено на heroku.com:

[F2-Final](https://finaljob2021.herokuapp.com/)

Права пользователей разделены на три типа:

 - admin   (superuser)

 - HR      (создаёт/редактирует/анализирует опрос/ы)

 - user    (отвечает на опрос/ы)

## Доступ к приложению:

admin:

    Admin

    7654321

HR:

    pupkin

    vasya

user:

    user

    student2021


HR работает с опросами в админ-панели. Вопросы могут быть как с одним вариантом ответа, так и с нескольким + за ответы могут начисляться баллы. После прохождения опроса можно ознакомиться со стат.анализом в баллах. Юзеры могут регистрироваться и логиниться в приложении.

### Локальная установка

    python -m venv env

    env\scripts\activate.bat

    pip install -r requirements.txt

    python manage.py collectstatic

PostgreSQL:

    pip install postgresql

    CREATE DATABASE 

    CREATE USER admin WITH PASSWORD '...'

- дать админу разрешения: 

    GRANT ALL PRIVILEGES ON DATABASE nameyourbase_db TO admin

-установить используемый порт в файле settings.py

    python manage.py makemigrations

    python manage.py migrate

    python manage.py createsuperuser
    
    python manage.py runserver
    
    http://127.0.0.1:8000/