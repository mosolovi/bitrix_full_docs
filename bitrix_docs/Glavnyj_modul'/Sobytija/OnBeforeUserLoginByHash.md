[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserLoginByHash (с версии 4.0.6)

OnBeforeUserLoginByHash
=======================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool
функция-обработчик(
	array &arParams
)Копировать
```

Событие "OnBeforeUserLoginByHash" вызывается в методе [CUser::LoginByHash()](/api_help/main/reference/cuser/loginbyhash.php) до проверки имени входа **arParams*['LOGIN']*, хеша от пароля **arParams*['HASH']* и попытки авторизовать пользователя.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | Массив полей для проверки имени входа и пароля:  * **LOGIN** - Имя входа пользователя. * **HASH** - Специальный хеш от пароля пользователя. Данный хеш как правило хранится в куках пользователя. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены авторизации пользователя и прекращении выполнения метода [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserLoginByHash"](/api_help/main/events/onafteruserloginbyhash.php)
* [CUser::LoginByHash](/api_help/main/reference/cuser/loginbyhash.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserLoginByHash", Array("MyClass", "OnBeforeUserLoginByHashHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeUserLoginByHash"
	public static function OnBeforeUserLoginByHashHandler(&$arParams)
	{
		// здесь выполняем любые действия связанные 
		if(strtolower($arParams['LOGIN'])=="guest")
		{
			global $APPLICATION;
			$APPLICATION->throwException("Пользователь с именем входа Guest не может авторизоваться по хешу.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: