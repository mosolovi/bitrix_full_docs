[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockPropertyUpdate (доступно с 4.0.6)

OnBeforeIBlockPropertyUpdate
============================

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

Событие вызывается в методе [CIBlockProperty::Update](/api_help/iblock/classes/ciblockproperty/update.php) до изменения свойства информационного блока,
и может быть использовано для отмены изменения или для переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#fproperty) изменяемого свойства информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены изменения и прекращении выполнения метода [CIBlockProperty::Update](/api_help/iblock/classes/ciblockproperty/update.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterIBlockPropertyUpdate"](/api_help/iblock/events/onafteriblockpropertyupdate.php)
* [CIBlockProperty::Update](/api_help/iblock/classes/ciblockproperty/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockPropertyUpdate", Array("MyClass", "OnBeforeIBlockPropertyUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockPropertyUpdate"
	public static function OnBeforeIBlockPropertyUpdateHandler(&$arFields)
	{
		if(strlen($arFields["CODE"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Введите символьный код. (ID:".$arFields["ID"].")");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: