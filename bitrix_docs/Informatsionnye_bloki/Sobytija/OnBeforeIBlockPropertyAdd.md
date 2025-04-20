[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockPropertyAdd (доступно с 4.0.6)

OnBeforeIBlockPropertyAdd
=========================

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

Событие вызывается в методе [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php) до вставки свойства в инфоблок,
и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#fproperty) нового свойства информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterIBlockPropertyAdd"](/api_help/iblock/events/onafteriblockpropertyadd.php)
* [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockPropertyAdd", Array("MyClass", "OnBeforeIBlockPropertyAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockPropertyAdd"
	public static function OnBeforeIBlockPropertyAddHandler(&$arFields)
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