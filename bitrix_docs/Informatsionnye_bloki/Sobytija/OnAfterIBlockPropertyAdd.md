[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockPropertyAdd (доступно с 4.0.6)

OnAfterIBlockPropertyAdd
========================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array &arFields
);Копировать
```

Событие "OnAfterIBlockPropertyAdd" вызывается после попытки добавления нового свойства информационного блока методом [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#fproperty) нового свойства информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [Событие "OnBeforeIBlockPropertyAdd"](/api_help/iblock/events/onbeforeiblockpropertyadd.php)
* [CIBlockProperty::Add](/api_help/iblock/classes/ciblockproperty/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockPropertyAdd", Array("MyClass", "OnAfterIBlockPropertyAddHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockPropertyAdd"
	public static function OnAfterIBlockPropertyAddHandler(&$arFields)
	{
		if($arFields["ID"]>0)
			AddMessage2Log("Запись с кодом ".$arFields["ID"]." добавлена.");
		else
			AddMessage2Log("Ошибка добавления записи (".$arFields["RESULT_MESSAGE"].").");
	}
}
?>Копировать
```

Новинки документации в соцсетях: