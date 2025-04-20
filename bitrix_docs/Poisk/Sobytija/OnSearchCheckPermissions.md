[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnSearchCheckPermissions (доступен с 8.0.4)

OnSearchCheckPermissions
========================

```
void
функция-обработчик(
	string FIELD
);Копировать
```

Событие "OnSearchCheckPermissions" вызывается при построении поискового запроса. Позволяет задать дополнительные условия для определения прав доступа к результатам поиска.

#### Параметры

| Параметр | Описание |
| --- | --- |
| FIELD | Столбец таблицы поискового индекса для использования в подзапросе (например: SC.ID или scsite.SEARCH\_CONTENT\_ID). |

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

Новинки документации в соцсетях: