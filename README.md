# Api_YaTube
API для социальной сети [YaTube](https://github.com/Alex9568rus/hw05_final)

В YaTube можно:
* опубликовывать/редактировать/удалять посты
* комментировать
* подписываться на аторов 

Для аутентификации используются JWT-токены.
___

# Автор
Жбаков Александр
___

# Технологии:
* Django 2.2.16
* Python 3.9
* Djangorestframework 3.12.4

___

# Запуск проекта:

1. Клонируйте репозитроий с проектом:

    ```git clone git@github.com:Alex9568rus/api_final_yatube.git```
2. Перейдите в созданную директорию, установите виртуальное окружение, активируйте его и установите необходимые зависимости:
    1. `cd api_final_yatube`
    2. - `python3 -m venv venv`
       - `source venv/bin/activate`
       - `python3 -m pip install --upgrade pip`
       - `pip install -r requirements.txt`
3. Установите дополнительные компоненты:
    - `pip install django-filter`
    - `pip install djoser djangorestframework-simplejwt==4.7.2`
4. Выполните миграции:
    - `cd yatube_api`
    - `python3 manage.py migrate`
5. запустите проект:

    `python3 manage.py runserver`
    
После запуска проекта документация доступна по адресу: [http://127.0.0.1:8000/redoc/](http://127.0.0.1:8000/redoc/). В ней описаны возможные запросы к API и структура ожидаемых ответов. Для каждого запроса указаны уровни прав доступа: пользовательские роли, которым разрешён запрос.
____

# Примеры запросов/ответов:

**1. GET /api/v1/posts/**

***Response:***
    
```
{
    "id": 0,
    "author": "alex",
    "text": "text_post",
    "pub_date": "2022-04-12T15:03:22Z",
    "image": "image",
    "group": 0
}
```

**2. POST /api/v1/posts/**

***Request:***
    
```
{
    "text": "some_text",
    "image": "pic",
    "group": 1
}
```

***Response:***

```
{
    "id": 0,
    "author": "username",
    "text": "some_text",
    "pub_date": "2022-04-12T15:17:10Z",
    "image": "pic",
    "group": 1
}
```
