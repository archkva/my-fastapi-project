# my-fastapi-project

Проект содержит два сервиса: todo_app и shorturl_app.

# TODO сервис
Сервис для управления задачами.

## Функционал
- Создание, редактирование, удаление задач;
- Получение списка задач.

## Установка локально
- Клонируйте репозиторий:
```git clone https://github.com/archkva/my-fastapi-project.git```

- Создайте образ:
```docker build -t [название образа (e.g. todo_app)] [путь до склонированного репозитория/todo_app]```

- Разверните контейнер с образом:
```docker run -d -p [адрес порта, по умолчанию 8000:80] —name [название контейнера, e.g. todo] -v todo_data:/app/data [название образа]```

## Установка через Docker Hub
- Разверните контейнер, используя образ из удаленного репозитория на Docker Hub:
```docker run -d -p [адрес порта, по умолчанию 8000:80] —name [название контейнера, e.g. todo] -v todo_data:/app/data archkva/todo_app:latest```

## Примеры API-запросов
1. Создание задачи:
POST /items
Тело запроса:
```
{
  "title": "Walk the dog",
  "description": "Take the dog for a walk",
  "completed": false
}
```

3. Получение списка задач:
GET /items
4. Получение задачи по ID:
GET /items/{item_id}
5. Обновление задачи по ID:
PUT /items/{item_id}:
6. Удаление задачи по ID:
DELETE /items/{item_id}


# Short URL сервис

## Функционал
- Создание, удаление сокращенных ссылок;
- Получение информации о ссылках.

## Установка локально
- Клонируйте репозиторий:
```git clone https://github.com/archkva/my-fastapi-project.git```

- Создайте образ:
```docker build -t [название образа (e.g. short_url_app)] [путь до склонированного репозитория/shorturl_app]```

- Разверните контейнер с образом:
```docker run -d -p [адрес порта, по умолчанию 8001:80] —name [название контейнера, e.g. short_url] -v short_url_data:/app/data [название образа]```

## Установка через Docker Hub
- Разверните контейнер, используя образ из удаленного репозитория на Docker Hub:
```docker run -d -p [адрес порта, по умолчанию 8001:80] —name [название контейнера, e.g. short_url] -v short_url:/app/data archkva/shorturl_app:latest```

## Примеры API-запросов
1. Генерирование сокращенной ссылки:
POST /shorten
Тело запроса:
```
{
  "url": "https://github.com/archkva/my-fastapi-project"
}
```

2. Перенаправление на полный URL, если он существует:
GET /items
3. Получение JSON с информацией о полном URL:
GET /stats/{short_id}
4. Удаление ссылки:
DELETE /{short_id}

