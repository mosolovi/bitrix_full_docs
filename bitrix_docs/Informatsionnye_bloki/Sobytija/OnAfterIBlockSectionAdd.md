[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockSectionAdd (доступно с 4.0.6)

OnAfterIBlockSectionAdd
=======================

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

Событие "OnAfterIBlockSectionAdd" вызывается после попытки добавления нового раздела информационного блока методом [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#fsection) нового раздела информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [Событие "OnBeforeIBlockSectionAdd"](/api_help/iblock/events/onbeforeiblocksectionadd.php)
* [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockSectionAdd", Array("MyClass", "OnAfterIBlockSectionAddHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockSectionAdd"
	public static function OnAfterIBlockSectionAddHandler(&$arFields)
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