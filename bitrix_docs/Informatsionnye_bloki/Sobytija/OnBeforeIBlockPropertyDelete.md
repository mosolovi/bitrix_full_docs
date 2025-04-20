[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockPropertyDelete (доступно с 4.0.6)

OnBeforeIBlockPropertyDelete
============================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool
функция-обработчик(
	int ID
);Копировать
```

Событие "OnBeforeIBlockPropertyDelete" вызывается перед удалением свойства методом [CIBlockProperty::Delete](/api_help/iblock/classes/ciblockproperty/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *ID* | ID удаляемого свойства. |

#### Возвращаемое значение

Для отмены удаления свойства и прекращении выполнения метода [CIBlockProperty::Delete](/api_help/iblock/classes/ciblockproperty/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [CIBlockProperty::Delete](/api_help/iblock/classes/ciblockproperty/delete.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockPropertyDelete", Array("MyClass", "OnBeforeIBlockPropertyDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockPropertyDelete"
	public static function OnBeforeIBlockPropertyDeleteHandler($ID)
	{
		if($ID==1)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Свойство с ID=1 нельзя удалить.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: