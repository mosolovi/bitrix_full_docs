[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSmile](/api_help/forum/developer/cforumsmile/index.php)

Add (доступен с 3.3.3)

Add
===

```
int
Add(
	array arFields
);Копировать
```

Создает новый смайл с параметрами, указанными в массиве *arFields*. Возвращает код созданного смайла. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей смайла](/api_help/forum/fields.php#cforumsmile). В специальное поле "LANG" заносится массив массивов полей языковых параметров смайла, которые имеют аналогичную структуру. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Возвращает код созданного смайла. В случае ошибки добавления возвращает False.

#### Смотрите также

* [Поля смайла](/api_help/forum/fields.php#cforumsmile)

Новинки документации в соцсетях: