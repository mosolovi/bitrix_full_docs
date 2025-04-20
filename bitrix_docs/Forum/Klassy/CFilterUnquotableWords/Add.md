[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterUnquotableWords](/api_help/forum/developer/cfilterunquotablewords/index.php)

Add (доступен с 5.1.0)

Add
===

```
int
Add(
	array arFields
);Копировать
```

Создает новую запись с параметрами, указанными в массиве *arFields*. Возвращает код созданной записи. Метод нестатический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Словарь слов"](/api_help/forum/fields.php#cfilterunquotablewords). Обязательные поля должны быть заполнены. | 5.1.0 |

#### Возвращаемое значение

Возвращает код созданной записи. В случае ошибки добавления возвращает False.

#### Смотрите также

* таблица ["Словарь слов"](/api_help/forum/fields.php#cfilterunquotablewords)

Новинки документации в соцсетях: