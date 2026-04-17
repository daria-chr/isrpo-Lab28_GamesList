# Лабораторная работа №28. Веб-сервер на C#: список любимых игр с полным управлением

ASP.NET Core Web API для управления списком любимых игр. Поддерживает полный набор CRUD-операций: получение, добавление, обновление и удаление игр.

## Запуск

```bash
cd GamesApi
dotnet run
```

## Маршруты API

|Метод |Маршрут              |Описание                      |Статус   |
|------|---------------------|------------------------------|---------|
|GET   |/api/games           |Получить все игры             |200      |
|GET   |/api/games/{id}      |Получить игру по id           |200 / 404|
|GET   |/api/games/favourites|Получить только избранные игры|200      |
|POST  |/api/games           |Добавить игру                 |201 / 400|
|DELETE|/api/games/{id}      |Удалить игру                  |204 / 404|
|PUT   |/api/games/{id}      |Обновить игру                 |200 / 404|

## Примеры curl-команд

### Получить все игры

```bash
curl http://localhost:5000/api/games
```

### Получить игру по id

```bash
curl http://localhost:5000/api/games/1
```

### Получить избранные игры

```bash
curl http://localhost:5000/api/games/favourites
```

### Добавить игру

```bash
curl -X POST http://localhost:5000/api/games \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Sims 4\", \"genre\": \"Simulation\", \"releaseYear\": 2017, \"isFavourite\": true}"
```

### Обновить игру

```bash
curl -X PUT http://localhost:5000/api/games/2 \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Sims 4\", \"genre\": \"Simulation\", \"releaseYear\": 2017, \"isFavourite\": true}"
```

### Удалить игру

```bash
curl -X DELETE http://localhost:5000/api/games/1
```

### Проверить статусный код ответа

```bash
curl -i http://localhost:5000/api/games/99
```


---
Автор: Черкина Дарья

Группа: ИСП-231