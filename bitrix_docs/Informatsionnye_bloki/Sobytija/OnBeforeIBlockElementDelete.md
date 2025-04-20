[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockElementDelete (доступно с 4.0.6)

OnBeforeIBlockElementDelete
===========================

Включить вкладки

Описание и параметры

Пример функции-обработчика

Смотрите также

### Описание и параметры

```
bool
функция-обработчик(
	int ID
);Копировать
```

Событие "OnBeforeIBlockElementDelete" вызывается перед удалением элемента методом [CIBlockElement::Delete](/api_help/iblock/classes/ciblockelement/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *ID* | ID удаляемого элемента. |

#### Возвращаемое значение

Для отмены удаления элемента и прекращении выполнения метода [CIBlockElement::Delete](/api_help/iblock/classes/ciblockelement/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockElementDelete", Array("MyClass", "OnBeforeIBlockElementDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockElementDelete"
	public static function OnBeforeIBlockElementDeleteHandler($ID)
	{
		if($ID==1)
		{
			global $APPLICATION;
			$APPLICATION->throwException("элемент с ID=1 нельзя удалить.");
			return false;
		}
	}
}
?>Копировать
```

### Смотрите также

* [CIBlockElement::Delete](/api_help/iblock/classes/ciblockelement/delete.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

Новинки документации в соцсетях: