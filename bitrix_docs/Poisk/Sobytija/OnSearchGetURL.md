[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnSearchGetURL (доступен с 4.0.0)

OnSearchGetURL
==============

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
string
функция-обработчик(
	array arFields
);Копировать
```

Событие "OnSearchGetURL" вызывается при форматировании элемента в результатах поиска из метода [CSearch::Fetch](/api_help/search/classes/csearch/fetch.php) и при построении Google Sitemap [CSiteMap::Create](/api_help/search/classes/csitemap/create.php). На данный момент событие вызывается только для параметризированных URL.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | Массив описывающий элемент поискового индекса. |

#### Возвращаемое значение

Функция-обработчик может применить форматирование к элементу URL. И должна его вернуть даже если форматирование не было применено.

### Смотрите также

* [CSearch::Fetch](/api_help/search/classes/csearch/fetch.php)
* [CSiteMap::Create](/api_help/search/classes/csitemap/create.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
//init.php
// регистрируем обработчик события "OnSearchGetURL" модуля "search"
AddEventHandler("search", "OnSearchGetURL", array("CMyClass", "OnSearchGetURL"));
class CMyClass
{
	public static function OnSearchGetURL($arFields)
	{
		$url = str_replace("#MY_SID#", md5(rand()), $arFields["URL"]);
		return $url;
	}
}
?>Копировать
```

Новинки документации в соцсетях: