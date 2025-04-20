[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserLogin (с версии 4.0.6)

OnBeforeUserLogin
=================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool
функция-обработчик(
	array &arParams
);Копировать
```

Событие "OnBeforeUserLogin" вызывается в методе [CUser::Login](/api_help/main/reference/cuser/login.php) до проверки имени входа **arParams*['LOGIN']* и пароля **arParams*['PASSWORD']*  и попытки авторизовать пользователя,
и может быть использовано для прекращения процесса проверки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | Массив полей для проверки имени входа и пароля:  * **LOGIN** - Логин пользователя * **PASSWORD** - Пароль. Если параметр **PASSWORD\_ORIGINAL** равен"Y", то в данном параметре был передан оригинальный пароль, в противном случае был передан хеш (md5) от оригинального пароля. * **REMEMBER** - Если значение равно "Y", то авторизация пользователя должна быть сохранена в куках. * **PASSWORD\_ORIGINAL** - Если значение равно "Y", то это означает что **PASSWORD** не был сконвертирован в MD5 (т.е. в параметре **PASSWORD** был передан реальный пароль вводимый пользователем с клавиатуры), если значение равно "N", то это означает что **PASSWORD** уже сконвертирован в MD5. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены авторизации пользователя и прекращении выполнения метода [CUser::Login](/api_help/main/reference/cuser/login.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserLogin"](/api_help/main/events/onafteruserlogin.php)
* [CUser::Login](/api_help/main/reference/cuser/login.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserLogin", Array("MyClass", "OnBeforeUserLoginHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeUserLogin"
	public static function OnBeforeUserLoginHandler(&$arFields)
	{
		// здесь выполняем любые действия связанные 
		if(strtolower($arFields["LOGIN"])=="guest")
		{
			global $APPLICATION;
			$APPLICATION->throwException("Пользователь с именем входа Guest не может быть авторизован.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: