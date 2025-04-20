[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBlogUpdate (5.0.2)

OnBlogUpdate
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	int   ID
	array &arParams 
);Копировать
```

Событие вызывается в момент изменения блога.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого блога. |
| arParams | [Массив полей](/api_help/blogs/fields.php#blog) блога. |

#### Смотрите также

* [Событие "OnBeforeBlogUpdate"](/api_help/blogs/events/onbeforeblogupdate.php)
* [CBlog::Update](/api_help/blogs/classes/cblog/update.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog", 
	"OnBlogUpdate", 
	Array("MyClass", "OnBlogUpdateHandler")
);
class MyClass
{
	// создаем обработчик события "OnBlogUpdate"
	public static function OnBlogUpdateHandler($ID, &$arFields)
	{
		...
	}
}
?>Копировать
```

Новинки документации в соцсетях: