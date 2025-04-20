[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterDictionary](/api_help/forum/developer/cfilterdictionary/index.php)

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

Изменяет параметры существующего словаря с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемого словаря. Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код записи, параметры которой необходимо изменить. |  |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Словарь"](/api_help/forum/fields.php#cfilterdictionary). |  |

#### Возвращаемое значение

Возвращает код измененного словаря. В случае ошибки изменения возвращает False.

#### Смотрите также

* поля таблицы ["Словарь"](/api_help/forum/fields.php#cfilterdictionary)

Новинки документации в соцсетях: