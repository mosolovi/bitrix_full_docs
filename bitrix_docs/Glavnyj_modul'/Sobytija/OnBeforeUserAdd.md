[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserAdd (с версии 4.0.16)

OnBeforeUserAdd
===============

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

Событие вызывается в методе [CUser::Add](/api_help/main/reference/cuser/add.php) до вставки нового пользователя,
и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/main/reference/cuser/index.php#fuser) нового пользователя. |

**Примечание**. Все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CUser::Add](/api_help/main/reference/cuser/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterUserAdd"](/api_help/main/events/onafteruseradd.php)
* [CUser::Add](/api_help/main/reference/cuser/add.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserAdd", Array("MyClass", "OnBeforeUserAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeUserAdd"
	public static function OnBeforeUserAddHandler(&$arFields)
	{
		if(strlen($arFields["LAST_NAME"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Пожалуйста, введите фамилию.");
			return false;
		}
	}
}
?>Копировать
```

Автоматическое создание логина пользователя на основе email (версия main меньше 20.0.0)

```
<?
use Bitrix\Main\EventManager,
	Bitrix\Main\Diag\Debug,
	Bitrix\Main\Context;
$eventManager = EventManager::getInstance();
/* ---------------------------------------------------------------------------------------------------- EMAIL to LOGIN */
$eventManager->addEventHandler('main', 'OnBeforeUserAdd', ['CUserEx', 'OnBeforeUserAddHandler']);
$eventManager->addEventHandler('main', 'OnBeforeUserRegister', ['CUserEx', 'OnBeforeUserRegisterHandler']);
$eventManager->addEventHandler('main', 'OnBeforeUserUpdate', ['CUserEx', 'OnBeforeUserUpdateHandler']);
class CUserEx
{
	function OnBeforeUserAddHandler( &$arFields )
	{
		//\Bitrix\Main\Diag\Debug::writeToFile( $arFields, 'OnBeforeUserAddHandler', 'log.txt');
		return self::OnBeforeUserUpdateHandler( $arFields );
	}
	function OnBeforeUserRegisterHandler( &$arFields )
	{
		//\Bitrix\Main\Diag\Debug::writeToFile( $arFields, 'OnBeforeUserRegisterHandler', 'log.txt');
		return self::OnBeforeUserUpdateHandler( $arFields );
	}
	function OnBeforeUserUpdateHandler( &$arFields )
	{
		//\Bitrix\Main\Diag\Debug::writeToFile( $arFields, 'OnBeforeUserUpdateHandler', 'log.txt');
		if( !\Bitrix\Main\Context::getCurrent()->getRequest()->isAdminSection() )
		{
			$arFields['LOGIN'] = $arFields['EMAIL'];
			//\Bitrix\Main\Diag\Debug::writeToFile( $arFields, 'OnBeforeUserUpdateHandler notAdminSection', 'log.txt');
			return $arFields;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: