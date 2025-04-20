[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockSectionAdd (доступно с 4.0.6)

OnBeforeIBlockSectionAdd
========================

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

Событие вызывается в методе [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php) до вставки информационного блока,
и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#fsection) нового раздела информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [Событие "OnAfterIBlockSectionAdd"](/api_help/iblock/events/onafteriblocksectionadd.php)
* [CIBlockSection::Add](/api_help/iblock/classes/ciblocksection/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockSectionAdd", Array("MyClass", "OnBeforeIBlockSectionAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockSectionAdd"
	public static function OnBeforeIBlockSectionAddHandler(&$arFields)
	{
		if(strlen($arFields["CODE"])<=0)
		{
			global $APPLICATION;
			$aMsg = array();
			$aMsg[] = array("id"=>"CODE", "text"=>"Введите символьный код.");
			$e = new CAdminException($aMsg);
			$APPLICATION->throwException($e);
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: