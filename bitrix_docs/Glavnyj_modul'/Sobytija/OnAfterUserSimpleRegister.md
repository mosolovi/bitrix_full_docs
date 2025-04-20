[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserSimpleRegister (с версии 4.0.6)

OnAfterUserSimpleRegister
=========================

Включить вкладки

Описание и параметры

Смотрите также

Примеры

### Описание и параметры

```
функция-обработчик(
	array &arFields,
);Копировать
```

Событие "OnAfterUserSimpleRegister" вызывается после попытки упрощённой регистрации нового пользователя методом [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arFields* | Массив полей регистрации нового пользователя:  * **USER\_ID** - в случае если регистрация прошла успешно содержит код нового пользователя * **RESULT\_MESSAGE** - массив с информационным текстом, описывающий результат регистрации пользователя, в дальнейшем используется функцией [ShowMessage](/api_help/main/functions/other/showmessage.php) для вывода сообщения. * **PASSWORD** - пароль * **CONFIRM\_PASSWORD** - подтверждение пароля * **CHECKWORD** - контрольное слово для смены пароля * **EMAIL** - EMail пользователя * **ACTIVE** - флаг активности [Y|N] * **SITE\_ID** - ID сайта по умолчанию для уведомлений * **GROUP\_ID** - массив ID групп пользователя * **USER\_IP** - IP адрес пользователя * **USER\_HOST** - хост пользователя |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.  
Это позволяет, например, изменить *RESULT\_MESSAGE*, что приведет к смене сообщения возвращаемого функцией [CUser::SimpleRegister](/api_help/main/reference/cuser/simpleregister.php).

### Смотрите также

* [Событие "OnBeforeUserSimpleRegister"](/api_help/main/events/onbeforeusersimpleregister.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [CUser::Register](/api_help/main/reference/cuser/register.php)

### Примеры

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnAfterUserSimpleRegister"
RegisterModuleDependences("main", "OnAfterUserSimpleRegister", "my_module_id", "MyClass", "OnAfterUserSimpleRegisterHandler");
?>Копировать
```

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnAfterUserSimpleRegister"
	public static function OnAfterUserSimpleRegisterHandler(&$fields)
	{
		// если регистрация успешна то
		if($fields["USER_ID"]>0)
		{
			// зададим сообщение об успешной регистрации
			$fields["RESULT_MESSAGE"]["MESSAGE"] = "Вы успешно зарегистрировались на сайте. Ваш логин - ".$fields["LOGIN"];
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: