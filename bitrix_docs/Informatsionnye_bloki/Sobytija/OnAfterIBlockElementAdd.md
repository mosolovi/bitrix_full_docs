[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockElementAdd (доступно с 4.0.6)

OnAfterIBlockElementAdd
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

Событие "OnAfterIBlockElementAdd" вызывается после попытки добавления нового элемента информационного блока методом [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php). Работает вне зависимости от того были ли созданы/изменены элементы непосредственно, поэтому необходимо дополнительно проверять параметр: RESULT\_MESSAGE.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/iblock/fields.php#felement) нового элемента информационного блока. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

**Примечания:**

* Событие *OnAfterIBlockElementAdd* будет вызываться в любом случае, даже если в [OnBeforeIBlockElementAdd](/api_help/iblock/events/onbeforeiblockelementadd.php) сработало исключение и элемент добавлен не был. Узнать о том, что добавление было отменено в событии *OnAfterIBlockElementAdd* можно с помощью *arFields["RESULT"]*. Если добавление прошло успешно, в нем будет храниться ID элемента, иначе - false.
* Если была загружена картинка для анонса или детальная картинка, то в *arFields["PREVIEW\_PICTURE"]* (*arFields["DETAIL\_PICTURE"]*) хранится исходный временный файл (из папки temp) в формате:

  ```
  (
  	[name] => 3323207.jpg
  	[type] => image/jpeg
  	[tmp_name] => /tmp/phpAU0r3o
  	[error] => 0
  	[size] => 577894
  	[del] => 
  	[description] => 
  	[MODULE_ID] => iblock
  )Копировать
  ```

  При этом реальный файл, который привязан к элементу, не указывается. В то же время в массив *arFields* передается ключ *"PREVIEW\_PICTURE\_ID"* (*"DETAIL\_PICTURE"*), в нём хранится ID привязанного к элементу файла.

### Смотрите также

* [Событие "OnBeforeIBlockElementAdd"](/api_help/iblock/events/onbeforeiblockelementadd.php)
* [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnAfterIBlockElementAdd", Array("MyClass", "OnAfterIBlockElementAddHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterIBlockElementAdd"
	public static function OnAfterIBlockElementAddHandler(&$arFields)
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