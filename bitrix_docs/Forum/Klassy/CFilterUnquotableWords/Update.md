[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterUnquotableWords](/api_help/forum/developer/cfilterunquotablewords/index.php)

Update (доступен с 5.1.0)

Update
======

```
int
Update(
	int ID,
	array arFields
);Копировать
```

Изменяет параметры существующей записи с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемой записи. Метод нестатический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код записи, параметры которой необходимо изменить. | 5.1.0 |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Словарь слов"](/api_help/forum/fields.php#cfilterunquotablewords). | 5.1.0 |

#### Возвращаемое значение

Возвращает код измененной записи. В случае ошибки изменения возвращает False.

#### Смотрите также

* таблица ["Словарь слов"](/api_help/forum/fields.php#cfilterunquotablewords)

Новинки документации в соцсетях: