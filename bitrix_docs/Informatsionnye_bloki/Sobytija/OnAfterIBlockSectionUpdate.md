[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockSectionUpdate (доступно с 4.0.6)

OnAfterIBlockSectionUpdate
==========================

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

Событие "OnAfterIBlockSectionUpdate" вызывается после попытки изменения раздела информационного блока методом [CIBlockSection::Update](/api_help/iblock/classes/ciblocksection/update.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#fsection) изменяемого раздела информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlockSection::Update](/api_help/iblock/classes/ciblocksection/update.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [Событие "OnBeforeIBlockSectionUpdate"](/api_help/iblock/events/onbeforeiblocksectionupdate.php)
* [CIBlockSection::Update](/api_help/iblock/classes/ciblocksection/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockSectionUpdate", Array("MyClass", "OnAfterIBlockSectionUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockSectionUpdate"
	public static function OnAfterIBlockSectionUpdateHandler(&$arFields)
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