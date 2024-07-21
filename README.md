# API для нахождения "точек-интереса"

Проект направлен на создание веб-сервиса для детекции углов ("точек-интереса") на изображениях с использованием алгоритма Харриса. API построено с использованием Django и Django REST Framework, обеспечивая простой и удобный доступ к функционалу детекции углов ("точек-интереса") через REST API.

**Содержание:**
- [Необходимые компоненты](#Необходимые-компоненты)
- [Создание виртуального окружения](#Создание-виртуального-окружения)
- [Установка необходимых библиотек](#Установка-необходимых-библиотек)
- [Локальный запуск API](#Локальный-запуск-API)
- [Запуск API при помощи Docker](#Запуск-API-при-помощи-Docker)

## Необходимые компоненты

* [Python 3.10.14](https://www.python.org/)
* [Mac or Linux environment (Я использую Anaconda)](https://www.anaconda.com/download)
* [Docker](https://www.docker.com/get-started/)

## Документация

* Техническое задание, составленное в соответствии с ГОСТ 19.201.
* Документация для взаимодействия с API в форме postman-коллекции.
* Документация API в формате Swagger.


## Создание виртуального окружения

Для корректной работы нам необъодим Python версии 3.10.14, установим его при помощи Anaconda:

```bash
conda create --name py310 python=3.10.14
```

После создания окружения нам необходимо его активировать:

```bash
conda activate py310
```

## Установка необходимых библиотек

Воспользуемся requrements.txt для установки необходимых библиотек:

```bash
pip install -r requirements.txt
```

## Локальный запуск API

Для выполнения миграций воспользуемся параметром migratre у manage.py:

```bash
python manage.py migrate
```

Для проверки тестов воспользуемся параметром test и qa у manage.py:

```bash
python manage.py test
```

```bash
python manage.py qa
```

Для запуска сервера воспользуемся параметром runserver у manage.py:

```bash
python manage.py runserver
```

- После запуска проект будет доступен по адресу [127.0.0.1:8000](http://127.0.0.1:8000)

- Для взаимодействия с документацией Swagger нужно перейти по адресу: [Документация-Swagger](http://127.0.0.1:8000/docs/swagger/)

- Postman-коллекция для работы с запросами находится в папке /docs/

## Запуск API при помощи Docker

Сборка Docker-образа и запуск контейнера:

```bash
docker-compose build      # Сборка контейнера
docker-compose up         # Запуск контейнера
```

Для выполнения миграций воспользуемся параметром migratre у manage.py:

```bash
python manage.py migrate
```

Для сбора статики:
```bash
python manage.py collectstatic --noinput
```

Для проверки тестов воспользуемся параметром test и qa у manage.py:

```bash
python manage.py test
```

```bash
python manage.py qa
```

Для запуска сервера воспользуемся параметром runserver у manage.py:

```bash
python manage.py runserver
```

- После запуска контейнера проект будет доступен по адресу [localhost:8000](http://localhost:8000)

Остановка Docker-контейнера:

```bash
docker-compose down -v      # с их удалением
docker-compose stop         # без удаления
```