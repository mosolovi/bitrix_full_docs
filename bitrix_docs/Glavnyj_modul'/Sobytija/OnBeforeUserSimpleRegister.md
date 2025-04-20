[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserSimpleRegister (с версии 4.0.6)

OnBeforeUserSimpleRegister
==========================

Включить вкладки

Описание и параметры

Смотрите также

Пример

### Описание и параметры

```
bool
функция-обработчик(
	array &arFields,
);Копировать
```

Событие "OnBeforeUserSimpleRegister" вызывается до попытки упрощённой регистрации нового пользователя методом [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php) и может быть использовано для прекращения процесса регистрации или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arFields* | Массив полей упрощённой регистрации нового пользователя:  * **PASSWORD** - пароль * **CONFIRM\_PASSWORD** - подтверждение пароля * **CHECKWORD** - контрольное слово для смены пароля * **EMAIL** - EMail пользователя * **ACTIVE** - флаг активности [Y|N] * **SITE\_ID** - ID сайта по умолчанию для уведомлений * **GROUP\_ID** - массив ID групп пользователя * **USER\_IP** - IP адрес пользователя * **USER\_HOST** - хост пользователя  На основании массива полей происходит добавление пользователя и отсылка почтового события NEW\_USER. |

  

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.  
Это позволяет, например, добавить в массив *fields* дополнительные регистрационные [поля](/api_help/main/reference/cuser/index.php) или, например, определить поле **LOGIN** - имя входа пользователя (в противном случае после регистрации пользователя логин будет заменен user**< ID нового пользователя>**") .

#### Возвращаемое значение

Для отмены авторизации пользователя и прекращении выполнения метода [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserSimpleRegister"](/api_help/main/events/onafterusersimpleregister.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [CUser::Register](/api_help/main/reference/cuser/register.php)

### Пример

```
<?
// файл /bitrix/php_interface/init.php
AddEventHandler(
	"main", 
	"OnBeforeUserSimpleRegister", 
	Array("MyClass", "OnBeforeUserSimpleRegisterHandler"), 
	100,
	$_SERVER["DOCUMENT_ROOT"]."/bitrix/php_interface/scripts/onbeforeusersimplereg.php"
);
?>
<?
// файл /bitrix/php_interface/scripts/onbeforeusersimplereg.php
class MyClass
{
	// создаем обработчик события "OnBeforeUserSimpleRegister"
	public static function OnBeforeUserSimpleRegisterHandler(&$arFields)
	{
		if (strpos($arFields["EMAIL"], "@mysite.com")===false)
		{
			global $APPLICATION;
			$APPLICATION->ThrowException("Регистрация возможно только для EMail адресов домена mysite.com");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: