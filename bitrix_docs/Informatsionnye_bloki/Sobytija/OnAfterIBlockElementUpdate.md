[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockElementUpdate (доступно с 4.0.6)

OnAfterIBlockElementUpdate
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

Событие "OnAfterIBlockElementUpdate" вызывается после попытки изменения элемента информационного блока методом [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php). Работает вне зависимости от того были ли созданы/изменены элементы непосредственно, то есть срабатывает даже после неудавшегося обновления. Поэтому необходимо дополнительно проверять параметр: RESULT\_MESSAGE.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#felement) изменяемого элемента информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки.   Массив полей элемента передается по ссылке. Любые манипуляции с этим массивом в рамках обработчика не изменят информацию об элементе инфоблока, сохраненную в БД. Однако, если в системе будет несколько обработчиков события, каждый последующий получит массив с изменениями. |

### Смотрите также

* [Событие "OnBeforeIBlockElementUpdate"](/api_help/iblock/events/onbeforeiblockelementupdate.php)
* [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockElementUpdate", Array("MyClass", "OnAfterIBlockElementUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockElementUpdate"
	public static function OnAfterIBlockElementUpdateHandler(&$arFields)
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