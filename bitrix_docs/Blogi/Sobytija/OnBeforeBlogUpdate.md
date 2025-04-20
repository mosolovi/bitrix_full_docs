[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBeforeBlogUpdate (5.0.2)

OnBeforeBlogUpdate
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	int   ID,
	array &arParams 
);Копировать
```

Событие вызывается в методе [CBlog::Update](/api_help/blogs/classes/cblog/update.php) до изменения блога и может быть использовано для отмены изменения или переопределения некоторых полей.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого блога. |
| arParams | [Массив полей](/api_help/blogs/fields.php#blog) блога. |

Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому, если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной, поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены изменения и прекращении выполнения метода [CBlog::Update](/api_help/blogs/classes/cblog/update.php), необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnBlogUpdate"](/api_help/blogs/events/onblogupdate.php)
* [CBlog::Update](/api_help/blogs/classes/cblog/update.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog", 
	"OnBeforeBlogUpdate", 
	Array("MyClass", "OnBeforeBlogUpdateHandler")
);
class MyClass
{
	// создаем обработчик события "OnBeforeBlogUpdate"
	public static function OnBeforeBlogUpdateHandler($ID, &$arFields)
	{
		if(strlen($arFields["DESCRIPTION"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Введите описание блога.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: