[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserAdd (с версии 4.0.16)

OnAfterUserAdd
==============

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array &arFields
);Копировать
```

Событие "OnAfterUserAdd" вызывается после попытки добавления нового пользователя методом [CUser::Add](/api_help/main/reference/cuser/add.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/main/reference/cuser/index.php#fuser) нового пользователя. Дополнительно, в элементе массива с индексом "RESULT" содержится результат работы (возвращаемое значение) метода [CUser::Add](/api_help/main/reference/cuser/add.php) и, в случае ошибки, элемент с индексом "RESULT\_MESSAGE" будет содержать текст ошибки. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Смотрите также

* [Событие "OnBeforeUserAdd"](/api_help/main/events/onbeforeuseradd.php)
* [CUser::Add](/api_help/main/reference/cuser/add.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnAfterUserAdd", Array("MyClass", "OnAfterUserAddHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterUserAdd"
	public static function OnAfterUserAddHandler(&$arFields)
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