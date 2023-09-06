# Kittygram

[workflow badge](https://github.com/smirnovds1990/kittygram_final/actions/workflows/main.yml/badge.svg)

Проект Киттиграм - это сайт, где пользователь может зарегистрироваться и выкладывать фотографии котов, а также просматривать фотографии других пользователей.
[Ссылка на сайт](https://kgram.sytes.net/)

## Технологии
- [Nginx](https://nginx.org/ru/)
- [Django](https://www.djangoproject.com/)
- [Gunicron](https://gunicorn.org/)
- [Python](https://www.python.org/)
- [Docker](https://www.docker.com/)
- [JavaScript](https://www.javascript.com/)

## Установка
Клонирование репозитория

```
git clone https://github.com/smirnovds1990/kittygram_final
```

[Установка Docker](https://www.docker.com/get-started/) - перейдите по ссылке, следуйте инструкциям в зависимости от вашей ОС.

После установки Docker:
- Открыть Docker Desktop
- Запустить сборку контейнеров:
```
docker compose up
```
либо
```
docker compose -f docker-compose.production.yml up
```
Простая команда ```docker compose up``` запускает сборку, следуя инструкции в файле по умолчанию - docker-compose.yml, используя Docker-файлы, находящиеся в директориях backend, frontend, nginx.

Команда с опциями ```docker compose -f docker-compose.production.yml up``` запускает сборку из файла docker-compose.production.yml, следуя инструкции которого, образы подгружаются с DockerHub, а не создаются локально.
- Сделать миграции и собрать статику (в новом окне терминала):
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```
```
sudo docker compose -f docker-compose.production.yml exec backend cp -r /kittygram_app/collected_static/. /backend_static/static
```
##### Если сборка запускается командой ```docker compose up```, использовать команды для сборки статики и миграции без опции ```-f docker-compose.production.yml```.
- Перейти на сайт: http://localhost:9000/

## Работа со скрытыми переменными
Для работы со скрытыми переменными используется библиотека python-decouple.
[Ссылка на документацию](https://pypi.org/project/python-decouple/)

Скрытые переменные хранятся в файле .env в директории infra_sprint1/backend/. Пример файла приведён в данной директории в файле .env.example.
```
DEBUG = True
SECRET_KEY = 'My_Secret_Key'
ALLOWED_HOSTS = 127.0.0.1, localhost
```
В файле настроек вызываются следующим образом:
```
from decouple import config, Csv
...
SECRET_KEY = config('SECRET_KEY', default='mykey')
DEBUG = config('DEBUG', cast=bool, default=False)
ALLOWED_HOSTS = config('ALLOWED_HOSTS', cast=Csv(), default='localhost')
```
Более подробную информацию по работе с библиотекой можно найти в документации по ссылке выше.

##### Автор проекта
[smirnovds](https://github.com/smirnovds1990)
