# praktikum_new_diplom
![foodgram-project-react workflow](https://github.com/Chist-Sergey/foodgram-project-react/actions/workflows/main.yml/badge.svg)

Демоверсия сайта: <http://84.201.162.161>


<h3> Установка и развертывание </h3>
После выполнения push необходимо зайти на сервер

    $ ssh yc-user@<IP адрес>

## Подготовка и запуск проекта
### Склонировать репозиторий на локальную машину:
```
git clone https://github.com/Chist-Sergey/foodgram-project-react
```
### Перейти в папку с проектом:
```
cd foodgram-project-react
```
### В папке **infra** создать файл .env с содержимым переменных окружения:

```
DB_ENGINE=db
POSTGRES_DB=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=postgres
DB_PORT=postgres
```

### Установка докер
https://docs.docker.com/engine/install/

### Запуск проекта из директории infra
``` docker-compose up -d --build ```Shell

### Создание миграций приложения пользователей
```docker-compose exec backend python manage.py makemigrations users```Shell

### Создание миграций приложения рецептов
```docker-compose exec backend python manage.py makemigrations api```Shell

### Сбор статики
```docker-compose exec backend python manage.py collectstatic --no-input```Shell

### Миграции
```docker-compose exec backend python manage.py migrate --noinput```Shell

### Cоздания суперпользователя 
``` docker-compose exec backend python manage.py createsuperuser ```Shell

### Заполнения базы начальными данными
``` docker-compose exec backend python manage.py loaddata fixtures/fixtures.json ```Shell

### Работал над проектом: Чистов С. В. - ученик Яндекс.Практикум
https://hub.docker.com/repository/docker/Chist-Sergey/foodgram - dockerhub

http://84.201.162.161/ - облако
