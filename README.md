# Kittygram

[![Github](https://raw.githubusercontent.com/tandpfun/skill-icons/59059d9d1a2c092696dc66e00931cc1181a4ce1f/icons/Github-Dark.svg)](https://github.com/smirnovds1990/kittygram_final)

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

 Установка виртуального окружения и зависимостей
```sh
cd backend
python -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
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
- Перейти на сайт: http://localhost:9000/

##### Автор проекта
[smirnovds](https://github.com/smirnovds1990)