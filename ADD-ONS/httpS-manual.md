#Устанавливаем https на сервер с сайтом:

 -посещаем сайт:

 [let's encrypt](https://letsencrypt.org/ru/getting-started/)

 -выбираем пункт "Приступить":

 -по SSH:

 [certbot](https://certbot.eff.org/)

 -выбираем "nginx" и "ОС" установленную на сервере:

 [certbot](https://certbot.eff.org/lets-encrypt/ubuntubionic-nginx)

 (4й пункт пропускаем, т.к. у нас чистый сервер)

 -принимаем условия "Accept all"

 -снова выбираем "ОС" установленную на сервере

 -перед установкой деактивируем виртуальное окружение! (venv)

##Установка:

 $ sudo apt update

 $ sudo apt install snapd

 $ sudo snap install core

 $ sudo snap install --classic certbot

 $ sudo ln -s /snap/bin/certbot /usr/bin/certbot

 $ sudo certbot --nginx

 -это автоустановка:

  --указываем "живой" email

  --принимаем условия: y/n

  --запрос на "расшаривание" Вашего email'а: y/n

  --вывод списка обнаруженных доменов и запрос какой  использовать (цифрами): 1

 -HTTPS установлен !!! (сертификат действителен на год, его можно продлять - шаг 8 в certbot'е)

###P.S.: CertBot прописывает в config Nginx'а сертификат, переадресовывая с 80 порта на 443.
