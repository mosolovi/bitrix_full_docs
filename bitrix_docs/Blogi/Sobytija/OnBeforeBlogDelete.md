[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBeforeBlogDelete (5.0.1)

OnBeforeBlogDelete
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	int   ID
);Копировать
```

Событие вызывается в методе [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php) до удаления блога и может быть использовано для отмены удаления.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор удаляемого блога. |

#### Возвращаемое значение

Для отмены удаления и прекращения выполнения метода [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnBlogDelete"](/api_help/blogs/events/onblogdelete.php)
* [CBlog::Delete](/api_help/blogs/classes/cblog/delete.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog",
	"OnBeforeBlogDelete", 
	Array("MyClass", "OnBeforeBlogDeleteHandler")
);
class MyClass
{
	// создаем обработчик события "OnBeforeBlogDelete"
	public static function OnBeforeBlogDeleteHandler($ID)
	{
		if(IntVal($ID) == 1)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Первый блог удалить нельзя.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: