[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnBeforeIndexDelete (доступен с 8.0.4)

OnBeforeIndexDelete
===================

```
void
функция-обработчик(
	string strWhere
);Копировать
```

Событие "OnBeforeIndexDelete" вызывается перед удалением части поискового индекса.

#### Параметры

| Параметр | Описание |
| --- | --- |
| strWhere | SQL условие для удаления. Представляет собой фильтр по полю SEARCH\_CONTENT\_ID. |

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeIndexDelete" модуля "search"
RegisterModuleDependences("search", "OnBeforeIndexDelete", "my_module", "CMyModule", "DeleteSearchExtData");
// создаем в модуле my_module в классе CMyModule функцию-метод TruncateTables
public static function DeleteSearchExData($strWhere)
{
	global $DB;
	$DB->Query("delete from my_search_ext_data where ".$strWhere);
}
?>Копировать
```

Новинки документации в соцсетях: