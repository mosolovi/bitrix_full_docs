[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockElementUpdate (доступно с 4.0.6)

OnBeforeIBlockElementUpdate
===========================

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

Событие вызывается в методе [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php) до изменения элемента информационного блока,
и может быть использовано для отмены изменения или для переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#felement) изменяемого элемента информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены изменения и прекращении выполнения метода [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterIBlockElementUpdate"](/api_help/iblock/events/onafteriblockelementupdate.php)
* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockElementUpdate", Array("MyClass", "OnBeforeIBlockElementUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockElementUpdate"
	public static function OnBeforeIBlockElementUpdateHandler(&$arFields)
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