[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

Update (доступно с 3.3.3)

Update
======

```
int
CForumUser::Update(
	int ID,
	array arFields [,
	string strUploadDir = false,
	int UpdateByUserId = false
);Копировать
```

Изменяет параметры существующего профайла с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемого профайла. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код профайла, параметры которого необходимо изменить. |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей профайла](/api_help/forum/fields.php#cforumuser). |  |
| strUploadDir | Каталог для загрузки файлов. Должен быть задан относительно главного каталога для загрузки. Необязательный. По умолчанию равен "forum". |  |
| UpdateByUserId | Необязательный. По умолчанию равен "false". | 4.0.3 |

#### Возвращаемое значение

Возвращает код измененного профайла. В случае ошибки изменения возвращает False.

#### Смотрите также

* [Поля профайла](/api_help/forum/fields.php#cforumuser)
* Перед изменением профайла следует проверить возможность изменения методом [CForumUser::CanUserUpdateUser](/api_help/forum/developer/cforumuser/canuserupdateuser.php)

Новинки документации в соцсетях: