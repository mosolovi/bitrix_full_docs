[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockSectionDelete (доступно с 4.0.6)

OnBeforeIBlockSectionDelete
===========================

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

Событие "OnBeforeIBlockSectionDelete" вызывается перед удалением раздела методом [CIBlockSection::Delete](/api_help/iblock/classes/ciblocksection/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *ID* | ID удаляемого раздела. |

#### Возвращаемое значение

Для отмены удаления раздела и прекращении выполнения метода [CIBlockSection::Delete](/api_help/iblock/classes/ciblocksection/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [CIBlockSection::Delete](/api_help/iblock/classes/ciblocksection/delete.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockSectionDelete", Array("MyClass", "OnBeforeIBlockSectionDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockSectionDelete"
	public static function OnBeforeIBlockSectionDeleteHandler($ID)
	{
		if($ID==1)
		{
			global $APPLICATION;
			$APPLICATION->throwException("раздел с ID=1 нельзя удалить.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: