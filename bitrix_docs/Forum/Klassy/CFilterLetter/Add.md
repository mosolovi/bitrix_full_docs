[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CFilterLetter](/api_help/forum/developer/cfilterletter/index.php)

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

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где     *field* - название поля;   *value* - значение поля.     Поля перечислены в списке полей таблицы ["Словарь транслита"](/api_help/forum/fields.php#cfilterletter). Обязательные поля должны быть заполнены. | 5.1.0 |

#### Возвращаемое значение

Возвращает код созданной записи. В случае ошибки добавления возвращает False.

#### Смотрите также

* таблица ["Словарь транслита"](/api_help/forum/fields.php#cfilterletter)

Новинки документации в соцсетях: