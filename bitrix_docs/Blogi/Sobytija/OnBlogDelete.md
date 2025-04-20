[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBlogDelete (5.0.1)

OnBlogDelete
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	int   ID
);Копировать
```

Событие вызывается в момент удаления блога.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор удаляемого блога. |

#### Смотрите также

* [Событие "OnBeforeBlogDelete"](/api_help/blogs/events/onbeforeblogdelete.php)
* [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog", 
	"OnBlogDelete",
	Array("MyClass", "OnBlogDeleteHandler")
);
class MyClass
{
	// создаем обработчик события "OnBlogDelete"
	public static function OnBlogDeleteHandler($ID)
	{
		...
	}
}
?>Копировать
```

Новинки документации в соцсетях: