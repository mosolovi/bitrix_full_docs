[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserUpdate (с версии 4.0.16)

OnAfterUserUpdate
=================

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

Событие **OnAfterUserUpdate** вызывается после попытки изменения свойств пользователя методом [CUser::Update](/api_help/main/reference/cuser/update.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | [Массив полей](/api_help/main/reference/cuser/index.php#fuser) изменяемого пользователя. Дополнительно, в элементе массива с индексом *RESULT* содержится результат работы (возвращаемое значение) метода [CUser::Update](/api_help/main/reference/cuser/update.php) и, в случае ошибки, элемент с индексом *RESULT\_MESSAGE* будет содержать текст ошибки. Если изменяется *$arFields["RESULT"]* на *false*, то необходимо устанавливать *$USER->LAST\_ERROR*. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому изменить эти параметры невозможно: изменения не сохраняются. Реально можно изменить только *RESULT\_MESSAGE*, что приведет к смене сообщения возвращаемого функцией [CUser::Register](/api_help/main/reference/cuser/register.php). Если необходимо модифицировать поля регистрации пользователя перед сохранением, необходимо использовать событие [OnBeforeUserRegister](/api_help/main/events/onbeforeuserregister.php)

### Смотрите также

* [Событие "OnBeforeUserUpdate"](/api_help/main/events/onbeforeuserupdate.php)
* [CUser::Update](/api_help/main/reference/cuser/update.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnAfterUserUpdate", Array("MyClass", "OnAfterUserUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterUserUpdate"
	public static function OnAfterUserUpdateHandler(&$arFields)
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