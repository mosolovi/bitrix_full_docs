[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserLogout (с версии 4.0.6)

OnAfterUserLogout
=================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array &arParams
);Копировать
```

Событие "OnAfterUserLogout" вызывается после [завершения авторизации](/api_help/main/reference/cuser/logout.php) пользователя.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arParams* | Массив параметров:  * **USER\_ID** - код пользователя * **SUCCESS** - результат операции: true, если авторизация завершена, false - в случае ошибки или отмены завершения авторизации обработчиком события [OnBeforeUserLogout](/api_help/main/events/onbeforeuserlogout.php). |

#### Смотрите также

* [Событие "OnBeforeUserLogout"](/api_help/main/events/onbeforeuserlogout.php)
* [CUser::Logout](/api_help/main/reference/cuser/logout.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnAfterUserLogout"
	public static function OnAfterUserLogoutHandler($arParams)
	{
		// здесь выполняем все что касается завершения авторизации
		...
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnAfterUserLogout"
RegisterModuleDependences("main", "OnAfterUserLogout", 
"my_module_id", "MyClass", "OnAfterUserLogoutHandler");
?>Копировать
```

Новинки документации в соцсетях: