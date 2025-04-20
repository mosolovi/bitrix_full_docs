[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumPrivateMessage](/api_help/forum/developer/cforumprivatemessage/index.php)

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

Изменяет параметры существующего сообщения с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемого сообщения. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код сообщения, параметры которого необходимо изменить. |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Приватное сообщение"](/api_help/forum/fields.php#cforumprivatemessage). |

#### Возвращаемое значение

Возвращает код измененного сообщения. В случае ошибки изменения возвращает False.

#### Смотрите также

* таблица ["Приватное сообщение"](/api_help/forum/fields.php#cforumprivatemessage)

Новинки документации в соцсетях: