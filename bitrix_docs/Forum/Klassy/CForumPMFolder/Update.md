[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPMFolder](/api_help/forum/developer/cforumpmfolder/index.php)

Update (доступен с 4.0.3)

Update
======

```
int
Update(
	int ID,
	array arFields
);Копировать
```

Изменяет параметры существующей папки пользователя с кодом *ID* на параметры, указанные в массиве *arFields*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код папки пользователя, параметры которой необходимо изменить. |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Папка пользователя"](/api_help/forum/fields.php#cforumpmfolder). |

#### Возвращаемое значение

Возвращает код измененного сообщения. В случае ошибки изменения возвращает False.

#### Смотрите также

* таблица ["Папка пользователя"](/api_help/forum/fields.php#cforumpmfolder)

Новинки документации в соцсетях: