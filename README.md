# Replacements

## API

### Authorization
```
Authorization: "Token <token>"
```
---

### ```/api/```
- [/api/img/](#apiimg)
- [/api/user/](#apiuser)
- [/api/docx/](#apidocx)
- [/api/time-table/](#apitime-table)


---
### ```/api/img/```

Работа с изображениями(звонки, замены)

Метод    |         Endpoint            |Параметры               | Описание
:-------:|-----------------------------|------------------------|---------
✅**POST** |```/api/img/upload/```       |``` file: <.jpg/png> ```|Добавляет в базу изображение/изображения, хеш функцию и дату добавления
✅**POST** |```/api/img/upload-bell/```       |``` file: <.jpg/png> ```|Добавляет в базу изображение с расписанием звонков
✅**GET**  |```/api/img/get-active/```   |       None             |Получение ссылки/ссылок на изображение/изображения активной замены
✅**GET**  |```/api/img/get-bell/```   |       None             |Получение ссылки на картинку с расписанием звонков



---
### ```/api/user/```
Пользователи

Метод    |         Endpoint                |Параметры               | Описание
:-------:|---------------------------------|------------------------|---------
✅**POST** |```/api/user/create/```        |```username: <str>``` </br>```password: <str>```</br>```access_key: <str>``` </br> Времмено: ```departament: <str>```| Создание аккаунта и автоматический вход в него
✅**POST** | ```/api/user/login/```        |```username: <str>``` </br>```password: <str>```| Вход в аккаунт
✅**POST** | ```/api/user/logout/```       | None | Выход из аккаунта
✅**GET** | ```/api/user/link/```          |   ```code: <int>```   |Привязка созданного аккаунта к аккаунту зачетной книжки
✅**POST**|```/api/user/generate-key/```   | ```username: <str>```  | Генерирует ключь доступа, для проверки требует username пользователя (роль-администратор)
✅**GET** |```/api/user/check-user/```      | None                 | Показывает данные пользователя

### ```/api/docx/```

Работа с документами

Метод    |         Endpoint             |   Параметры        | Описание
:-------:|------------------------------|--------------------|---------
✅**POST** |```/api/docx/upload-grid/```  |```file: <.docx>``` | Обновляет шаблон замен



### ```/api/time-table/```

Расписание

Метод    |         Endpoint             |   Параметры        | Описание
:-------:|------------------------------|--------------------|---------
✅**POST** |```/api/time-table/upload-table/```  |```file: <.xls/xltx/xlsx>``` </br> ```day: <str>``` ```even: <bool>``` | Парсит файл и заполняет базу дааных расписания
✅**GET** |```/api/time-table/get-active-table/```  |```group: <str>``` </br> ```day: <str> ``` </br>```even: <bool>``` </br> ```type: 'string' OR 'array' OR None```| Получает активное расписание 



