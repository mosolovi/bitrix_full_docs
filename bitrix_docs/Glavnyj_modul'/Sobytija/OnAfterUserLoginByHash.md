[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserLoginByHash (с версии 4.0.6)

OnAfterUserLoginByHash
======================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array &arParams
);Копировать
```

Событие "OnAfterUserLoginByHash" вызывается в методе [CUser::LoginByHash()](/api_help/main/reference/cuser/loginbyhash.php) после проверки имени входа **arParams*['LOGIN']* и хеша от пароля *arParams**['HASH']* и попытки авторизовать пользователя. В параметре *arParams**['USER\_ID']* будет передан код пользователя которого удалось авторизовать, а также массив с сообщением об ошибке **arParams*['RESULT\_MESSAGE']*.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | Массив полей проверки имени входа и пароля:  * **USER\_ID** - в случае, если авторизация прошла успешно, содержит код пользователя * **RESULT\_MESSAGE** - массив с информационным текстом, описывающий результат проверки пользователя, в дальнейшем используется функцией [ShowMessage](/api_help/main/functions/other/showmessage.php) для вывода сообщения. * **LOGIN** - Логин пользователя * **HASH** - Пароль. Специальный хеш от пароля пользователя. Данный хеш как правило хранится в куках пользователя. |

  

Некоторые параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.  
Это позволяет, например, изменить *RESULT\_MESSAGE*, что приведет к смене сообщения возвращаемого функцией [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php).

### Смотрите также

* [Событие "OnBeforeUserLoginByHash"](/api_help/main/events/onbeforeuserloginbyhash.php)
* [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnAfterUserLoginByHash", Array("MyClass", "OnAfterUserLoginByHashHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterUserLoginByHash"
	public static function OnAfterUserLoginByHashHandler(&$arParams)
	{
		if($arParams['USER_ID']<=0)
		{
			//переопределим сообщение об ошибке.
			$arParams['RESULT_MESSAGE'] = Array("MESSAGE" => "New error.", "TYPE" => "ERROR");
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: