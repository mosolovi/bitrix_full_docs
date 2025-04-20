[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnBeforeFullReindexClear (доступен с 8.0.4)

OnBeforeFullReindexClear
========================

```
void
функция-обработчик();Копировать
```

Событие "OnBeforeFullReindexClear" вызывается во время полной переиндексации. В начале первого шага, непосредственно перед удалением всех данных поискового индекса.

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeFullReindexClear" модуля "search"
RegisterModuleDependences("search", "OnBeforeFullReindexClear", "my_module", "CMyModule", "TruncateTables");
// создаем в модуле my_module в классе CMyModule функцию-метод TruncateTables
public static function TruncateTables()
{
	global $DB;
	$DB->Query("truncate table my_search_ext_data");
}
?>Копировать
```

Новинки документации в соцсетях: