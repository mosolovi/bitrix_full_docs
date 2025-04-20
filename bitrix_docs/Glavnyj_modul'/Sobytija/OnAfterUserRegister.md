[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserRegister (с версии 4.0.6)

OnAfterUserRegister
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры

### Описание и параметры

```
функция-обработчик(
	array &arFields
);Копировать
```

Событие "OnAfterUserRegister" вызывается после попытки регистрации нового пользователя методом [CUser::Register](/api_help/main/reference/cuser/register.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arFields* | Массив полей регистрации нового пользователя:  * **USER\_ID** - в случае если регистрация прошла успешно содержит код нового пользователя * **RESULT\_MESSAGE** - массив с информационным текстом, описывающий результат регистрации пользователя, в дальнейшем используется функцией [ShowMessage](/api_help/main/functions/other/showmessage.php) для вывода сообщения. * **LOGIN** - имя входа пользователя * **NAME** - имя пользователя * **LAST\_NAME** - фамилия пользователя * **PASSWORD** - пароль * **CONFIRM\_PASSWORD** - подтверждение пароля * **CHECKWORD** - новое контрольное слово для смены пароля * **EMAIL** - EMail пользователя * **ACTIVE** - флаг активности [Y|N] * **SITE\_ID** - ID сайта по умолчанию для уведомлений * **GROUP\_ID** - массив ID групп пользователя * **USER\_IP** - IP адрес пользователя * **USER\_HOST** - хост пользователя |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому изменить эти параметры невозможно: изменения не сохраняются. Реально можно изменить только *RESULT\_MESSAGE*, что приведет к смене сообщения возвращаемого функцией [CUser::Register](/api_help/main/reference/cuser/register.php). Если необходимо модифицировать поля регистрации пользователя перед сохранением, необходимо использовать событие [OnBeforeUserRegister](/api_help/main/events/onbeforeuserregister.php)

### Смотрите также

* [Событие "OnBeforeUserRegister"](/api_help/main/events/onbeforeuserregister.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493) в курсе Разработчик Bitrix Framework
* [CUser::Register](/api_help/main/reference/cuser/register.php)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnAfterUserRegister"
	public static function OnAfterUserRegisterHandler(&$arFields)
	{
		// если регистрация успешна то
		if($arFields["USER_ID"]>0)
		{
			// если текущий сайт - r1, то
			if(SITE_ID=="r1")
			{
				// зададим сообщение об успешной регистрации на сайте r1
				$arFields["RESULT_MESSAGE"]["MESSAGE"] = "Вы успешно зарегистрировались на сайте \"Мой любимый сайт 1\"";
			}
			elseif(SITE_ID=="r2")
			{
				// зададим сообщение об успешной регистрации на сайте r2
				$arFields["RESULT_MESSAGE"]["MESSAGE"] = "Вы успешно зарегистрировались на сайте \"Мой любимый сайт 2\"";
			}
		}
		return $arFields;
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnAfterUserRegister"
RegisterModuleDependences("main", "OnAfterUserRegister", "my_module_id", "MyClass", "OnAfterUserRegisterHandler");
?>Копировать
```

Новинки документации в соцсетях: