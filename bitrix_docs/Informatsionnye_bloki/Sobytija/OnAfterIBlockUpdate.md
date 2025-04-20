[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockUpdate (доступно с 4.0.6)

OnAfterIBlockUpdate
===================

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

Событие "OnAfterIBlockUpdate" вызывается после попытки изменения информационного блока методом [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#fiblock) изменяемого информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [Событие "OnBeforeIBlockUpdate"](/api_help/iblock/events/onbeforeiblockupdate.php)
* [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockUpdate", Array("MyClass", "OnAfterIBlockUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockUpdate"
	public static function OnAfterIBlockUpdateHandler(&$arFields)
	{
		if($arFields["RESULT"])
			AddMessage2Log("Запись с кодом ".$arFields["ID"]." изменена.");
		else
			AddMessage2Log("Ошибка изменения записи ".$arFields["ID"]." (".$arFields["RESULT_MESSAGE"].").");
	}
}
?>Копировать
```

Новинки документации в соцсетях: