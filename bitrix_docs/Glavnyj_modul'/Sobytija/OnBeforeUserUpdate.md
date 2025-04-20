[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserUpdate (с версии 4.0.16)

OnBeforeUserUpdate
==================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CUser::Update](/api_help/main/reference/cuser/update.php) до изменения параметров пользователя,
и может быть использовано для отмены изменения или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/main/reference/cuser/index.php#fuser) изменяемого пользователя. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены изменения и прекращении выполнения метода [CUser::Update](/api_help/main/reference/cuser/update.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserUpdate"](/api_help/main/events/onafteruserupdate.php)
* [CUser::Update](/api_help/main/reference/cuser/update.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserUpdate", Array("MyClass", "OnBeforeUserUpdateHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeUserUpdate"
	public static function OnBeforeUserUpdateHandler(&$arFields)
	{
		if(is_set($arFields, "LAST_NAME") && strlen($arFields["LAST_NAME"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Пожалуйста, введите фамилию. (ID:".$arFields["ID"].")");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: