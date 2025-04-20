[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserRegister (с версии 4.0.6)

OnBeforeUserRegister
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры

### Описание и параметры

```
bool
функция-обработчик(
	array &arArgs
);Копировать
```

Событие "OnBeforeUserRegister" вызывается до попытки регистрации нового пользователя методом [CUser::Register](/api_help/main/reference/cuser/register.php) и может быть использовано для прекращения процесса регистрации или переопределения некоторых полей.

**Примечание**: функция будет вызываться также при подтверждении регистрации (событие [OnBeforeUserUpdate](/api_help/main/events/onbeforeuserupdate.php)), где ключа LOGIN нет.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arArgs* | Массив полей регистрации нового пользователя:  * **LOGIN** - имя входа пользователя * **NAME** - имя пользователя * **LAST\_NAME** - фамилия пользователя * **PASSWORD** - пароль * **CONFIRM\_PASSWORD** - подтверждение пароля * **CHECKWORD** - новое контрольное слово для смены пароля * **EMAIL** - EMail пользователя * **ACTIVE** - флаг активности [Y|N] * **SITE\_ID** - ID сайта по умолчанию для уведомлений * **GROUP\_ID** - массив ID групп пользователя * **USER\_IP** - IP адресс пользователя * **USER\_HOST** - хост пользователя  На основании массива полей происходит добавление пользователя и отсылка почтового события NEW\_USER. |

**Примечание**. Массив значений данного обработчика является ссылкой на исходные переменные. Поэтому при изменении значения параметра или добавлении нового поля в массив внутри обработчика приведет к смене значения исходной переменной поступившей на вход функции-обработчика.
  
Это позволяет, например, добавить в массив *arArgs* дополнительные регистрационные [поля нового пользователя](/api_help/main/reference/cuser/index.php) или поля для почтового события NEW\_USER.

```
if ( isset($args['LOGIN']) && ! preg_match("/^[-a-zA-Z0-9_]+$/", $args['LOGIN']) )Копировать
```

#### Возвращаемое значение

Для отмены авторизации пользователя и прекращении выполнения метода [CUser::Register](/api_help/main/reference/cuser/register.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserRegister"](/api_help/main/events/onafteruserregister.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [CUser::Register](/api_help/main/reference/cuser/register.php)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnBeforeUserRegister"
	public static function OnBeforeUserRegisterHandler(&$arFields)
	{
		// если пользователь пришел по рекламной кампании #34, то
		if ($_SESSION["SESS_LAST_ADV_ID"]==34)
		{
			// добавляем его в группу #3
			$arFields["GROUP_ID"][] = 3;    
			// добавим административный комментарий
			if (intval($_SESSION["SESS_ADV_ID"])>0)
				$arFields["ADMIN_NOTES"] = "Рекламная кампания #34 - прямой заход";
			else
				$arFields["ADMIN_NOTES"] = "Рекламная кампания #34 - возврат";
			$arFields["SITE_ID"] = "ru";
		}
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeUserRegister"
RegisterModuleDependences("main", "OnBeforeUserRegister", "my_module_id", "MyClass", "OnBeforeUserRegisterHandler");
?>Копировать
```

Новинки документации в соцсетях: