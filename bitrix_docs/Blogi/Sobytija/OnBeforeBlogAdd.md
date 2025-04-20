[Блоги](/api_help/blogs/index.php)

[События](/api_help/blogs/events/index.php)

OnBeforeBlogAdd (5.0.2)

OnBeforeBlogAdd
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CBlog::Add](/api_help/blogs/classes/cblog/add.php) до вставки блога, и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arParams | [Массив полей](/api_help/blogs/fields.php#blog) блога. |

Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому, если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной, поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CBlog::Add](/api_help/blogs/classes/cblog/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnBlogAdd"](/api_help/blogs/events/onblogadd.php)
* [CBlog::Add](/api_help/blogs/classes/cblog/add.php)

### Примеры использования

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler(
	"blog", 
	"OnBeforeBlogAdd", 
	Array("MyClass", "OnBeforeBlogAddHandler")
);
class MyClass
{
	// создаем обработчик события "OnBeforeBlogAdd"
	public static function OnBeforeBlogAddHandler(&$arFields)
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