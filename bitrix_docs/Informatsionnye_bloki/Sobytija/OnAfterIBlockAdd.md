[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockAdd (доступно с 4.0.6)

OnAfterIBlockAdd
================

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

Событие "OnAfterIBlockAdd" вызывается после попытки добавления нового информационного блока методом [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#fiblock) нового информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Примечание:** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [Событие "OnBeforeIBlockAdd"](/api_help/iblock/events/onbeforeiblockadd.php)
* [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockAdd", Array("MyClass", "OnAfterIBlockAddHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockAdd"
	public static function OnAfterIBlockAddHandler(&$arFields)
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