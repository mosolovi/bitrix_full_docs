[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterUserAuthorize (с версии 4.0.6)

OnAfterUserAuthorize
====================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array user_fields
)Копировать
```

Обработчик события будет вызван из метода [CUser::Authorize](/api_help/main/reference/cuser/authorize.php) после авторизации пользователя, передавая в параметре *user\_fields* массив всех полей авторизованного пользователя.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *user\_fields* | Массив всех [полей пользователя](/api_help/main/reference/cuser/index.php). |

#### Смотрите также

* [CUser::Authorize](/api_help/main/reference/cuser/authorize.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Внешняя авторизация](http://dev.1c-bitrix.ru/learning/course/index.php?&COURSE_ID=43&LESSON_ID=3574)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnAfterUserAuthorize", Array("MyClass", "OnAfterUserAuthorizeHandler"));
class MyClass
{
	// создаем обработчик события "OnAfterUserAuthorize"
	public static function OnAfterUserAuthorizeHandler($arUser)
	{
		// выполняем все действия связанные с авторизацией
      
	}
}
?>Копировать
```

Новинки документации в соцсетях: