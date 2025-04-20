[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBlogAdd (5.0.2)

OnBlogAdd
=========

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

Событие вызывается в момент добавления блога.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор добавленного блога. |
| arParams | [Массив полей](/api_help/blogs/fields.php#blog) блога. |

#### Смотрите также

* [Событие "OnBeforeBlogAdd"](/api_help/blogs/events/onbeforeblogadd.php)
* [CBlog::Add](/api_help/blogs/classes/cblog/add.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog",
	"OnBlogAdd",
	Array("MyClass", "OnBlogAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBlogAdd"
	public static function OnBlogAddHandler($ID, &$arFields)
	{
		...
	}
}
?>Копировать
```

Новинки документации в соцсетях: