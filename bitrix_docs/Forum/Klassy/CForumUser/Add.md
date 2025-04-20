[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

Add (доступно с 3.3.3)

Add
===

```
int
CForumUser::Add(
	array arFields,
	string strUploadDir = false
);Копировать
```

Создает новый профайл с параметрами, указанными в массиве *arFields*. Возвращает код созданного профайла. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей профайла пользователя](/api_help/forum/fields.php#cforumuser). Обязательные поля должны быть заполнены. |  |
| strUploadDir | Каталог для загрузки файлов. Должен быть задан относительно главного каталога для загрузки. Необязательный. По умолчанию равен "forum". |  |

#### Возвращаемое значение

Возвращает код созданного профайла. В случае ошибки добавления возвращает False.

#### Смотрите также

* [Поля профайла](/api_help/forum/fields.php#cforumuser)
* Перед добавлением профайла следует проверить возможность добавления методом [CForumUser::CanUserAddUser](/api_help/forum/developer/cforumuser/canuseradduser.php)

Новинки документации в соцсетях: