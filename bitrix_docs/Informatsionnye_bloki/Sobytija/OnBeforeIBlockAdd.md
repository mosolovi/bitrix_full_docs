[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockAdd (доступно с 4.0.6)

OnBeforeIBlockAdd
=================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php) до вставки информационного блока,
и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#fiblock) нового информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterIBlockAdd"](/api_help/iblock/events/onafteriblockadd.php)
* [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockAdd", Array("MyClass", "OnBeforeIBlockAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockAdd"
	public static function OnBeforeIBlockAddHandler(&$arFields)
	{
		if(strlen($arFields["CODE"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Введите символьный код.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: