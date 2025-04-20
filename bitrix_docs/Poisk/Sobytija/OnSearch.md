[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnSearch (доступен с 3.0.4)

OnSearch
========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
функция-обработчик(
	string strQuery
);Копировать
```

Событие "OnSearch" вызывается перед выполнением поисковых запросов методом [CSearch::Search](/api_help/search/classes/csearch/search.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| strQuery | Поисковая фраза. Если используется поиск по тегам, то в начале добавляется "tags:". |

#### Возвращаемое значение

Функция обработчик может вернуть строку вида "параметр=значение" которая будет добавлена к
ссылкам на найденные элементы. Используется модулем статистики для учета поисковых фраз внутреннего поисковика.

### Смотрите также

* [CSearch::Search](/api_help/search/classes/csearch/search.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("search", "OnSearch", Array("MyClass", "OnSearchHandler"));
class MyClass
{
	// создаем обработчик события "BeforeIndex"
	public static function OnSearchHandler($strQuery)
	{
		if(strpos($strQuery, "tags:")!==false)
			return "tags_search=Y";
		else
			return "";
	}
}
?>Копировать
```

Новинки документации в соцсетях: