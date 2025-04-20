[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserLogin (с версии 4.0.6)

OnAfterUserLogin
================

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

Событие "OnAfterUserLogin" вызывается в методе [CUser::Login](/api_help/main/reference/cuser/login.php) после попытки авторизовать пользователя, проверив имя входа **arParams*['LOGIN']* и пароль **arParams*['PASSWORD']*.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | Массив полей проверки имени входа и пароля:  * **USER\_ID** - в случае если авторизация прошла успешно содержит код пользователя * **RESULT\_MESSAGE** - массив с информационным текстом, описывающий результат проверки пользователя, в дальнейшем используется функцией [ShowMessage](/api_help/main/functions/other/showmessage.php) для вывода сообщения. * **LOGIN** - Логин пользователя * **PASSWORD** - Пароль. Если параметр **PASSWORD\_ORIGINAL** равен"Y", то в данном параметре был передан оригинальный пароль, в противном случае был передан хеш (md5) от оригинального пароля. * **REMEMBER** - Если значение равно "Y", то авторизация пользователя должна быть сохранена в куках. * **PASSWORD\_ORIGINAL** - Если значение равно "Y", то это означает что **PASSWORD** не был сконвертирован в MD5 (т.е. в параметре **PASSWORD** был передан реальный пароль вводимый пользователем с клавиатуры), если значение равно "N", то это означает что **PASSWORD** уже сконвертирован в MD5. |

**Примечание**  
Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому, если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.  
Это позволяет, например, изменить *RESULT\_MESSAGE*, что приведет к смене сообщения возвращаемого функцией [CUser::Login](/api_help/main/reference/cuser/login.php).

### Смотрите также

* [Событие "OnBeforeUserLogin"](/api_help/main/events/onbeforeuserlogin.php)
* [CUser::Login](/api_help/main/reference/cuser/login.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
AddEventHandler("main", "OnAfterUserLogin", Array("MyClass", "OnAfterUserLoginHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterUserLogin"
	public static function OnAfterUserLoginHandler(&$fields)
	{
		// если логин не успешен то
		if($fields['USER_ID']<=0)
		{
			// счетчик неудавшихся попыток логина
			$_SESSION["AUTHORIZE_FAILURE_COUNTER"]++;
			// если количество неудачных попыток авторизации превышает 10, то
			if ($_SESSION["AUTHORIZE_FAILURE_COUNTER"]>10)
			{
				// ищем пользователя по логину
				$rsUser = CUser::GetByLogin($fields['LOGIN']);
				// и если нашли, то
				if ($arUser = $rsUser->Fetch())
				{
					// блокируем бюджет пользователя
					$user = new CUser;
					$user->Update($arUser["ID"],array("ACTIVE" => "N"));
					// задаем сообщение
					$fields['RESULT_MESSAGE'] = array("TYPE" => "ERROR", "MESSAGE" => "Ваш бюджет блокирован.");
				}
			}
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: