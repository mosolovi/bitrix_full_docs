[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnSearchGetTag (доступен с 7.1.2)

OnSearchGetTag
==============

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
string
функция-обработчик(
	string tag
);Копировать
```

Событие "OnSearchGetTag" вызывается при разборе строки тегов из функции [Tags\_prepare](/api_help/search/functions/tags_prepare.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| tag | Тег. |

#### Возвращаемое значение

Функция-обработчик может отфильтровать недопустимые символы или значения тега. И должна его вернуть даже если форматирование не было применено.

### Смотрите также

* [Tags\_prepare](/api_help/search/functions/tags_prepare.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
//init.php
// регистрируем обработчик события "OnSearchGetTag" модуля "search"
AddEventHandler("search", "OnSearchGetTag", array("CMyClass", "OnSearchGetTag"));
class CMyClass
{
	public static function OnSearchGetTag($tag)
	{
		static $stop = array(
			"АХ" => true,
			"ФУ" => true,
		);
		$tag = ToUpper($tag);
		if(array_key_exists($tag, $stop))
			return "";
		else
			return $tag;
	}
}
?>Копировать
```

Новинки документации в соцсетях: