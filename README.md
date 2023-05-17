#  API для Yatube

## Описание

API для Yatube - проект социальной сети в которой посредством программного интерфейса приложения является возможным: 

- Получать, создавать, обновлять и удалять публикаций.
- Получать, создавать, обновлять и удалять комментариеи к публикациям.
- Просматривать сообщества.
- Подписываться на авторов.
- Авторизовываться
## Стек технологий

* Python 3.11,
* Django 4.2,
* DRF,
* JWT + Djoser

## Запуск проекта в dev-режиме

- Клонировать репозиторий и перейти в него в командной строке.
- Установить и активируйте виртуальное окружение c учетом версии Python 3.7:

```bash
python -m venv venv
```

```bash
source venv/Scripts/activate
```

```bash
python -m pip install --upgrade pip
```

- Установить все зависимости из requirements.txt

```bash
cd yatube_api
```

```bash
pip install -r requirements.txt
```

- Выполнить миграции:

```bash
python manage.py migrate
```

- Создать суперпользователя:

```bash
python manage.py createsuperuser
```

- Запустить проект:

```bash
python manage.py runserver
```

## Примеры работы с API 

Для неавторизованных пользователей API доступен только в режиме чтения:

```r
GET api/v1/posts/ - получить список всех публикаций.
GET api/v1/posts/{id}/ - получение публикации по id
GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации
GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id
GET api/v1/groups/ - получение списка доступных сообществ
GET api/v1/groups/{id}/ - получение информации о сообществе по id
```

Для авторизованных пользователей доступны следующие действия
- Публикация поста:

```r
POST /api/v1/posts/
```

в body

```json
{
"text": "string",
"image": "string",
"group": 0
}
```

- Обновление публикации:

```r
PUT /api/v1/posts/{id}/
```

в body

```json
{
"text": "string",
"image": "string",
"group": 0
}
```

- Частичное обновление публикации:

```r
PATCH /api/v1/posts/{id}/
```

в body

```json
{
"text": "string",
"image": "string",
"group": 0
}
```
И другие. 