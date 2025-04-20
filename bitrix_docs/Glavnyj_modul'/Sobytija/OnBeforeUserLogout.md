[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserLogout (с версии 4.0.6)

OnBeforeUserLogout
==================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
bool
функция-обработчик(
	array &arParams
);Копировать
```

Вызывается перед завершением сеанса авторизации пользователя методом [CUser::Logout](/api_help/main/reference/cuser/logout.php) и может быть использовано для отмены завершения сеанса.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arParams* | Массив параметров:  * **USER\_ID** - код пользователя |

#### Смотрите также

* [Событие "OnAfterUserLogout"](/api_help/main/events/onafteruserlogout.php)
* [CUser::Logout](/api_help/main/reference/cuser/logout.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserLogout", Array("MyClass", "OnBeforeUserLogoutHandler"));
class MyClass
{
	public static function OnBeforeUserLogoutHandler($arParams)
	{
		if($arParams['ID']==10)
			return false;
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeUserLogout"
RegisterModuleDependences("main", "OnBeforeUserLogout", 
"my_module_id", "MyClass", "OnBeforeUserLogoutHandler");?>Копировать
```

Новинки документации в соцсетях: