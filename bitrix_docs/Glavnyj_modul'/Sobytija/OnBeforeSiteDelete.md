[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeSiteDelete (с версии 4.0.6)

OnBeforeSiteDelete
==================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
bool
функция-обработчик(
	string site_id
);Копировать
```

Событие "OnBeforeSiteDelete" вызывается перед [удалением сайта](/api_help/main/reference/csite/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление сайта.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *site\_id* | ID удаляемого сайта. |

#### Возвращаемое значение

Для отмены удаления сайта и прекращении выполнения метода [CSite::Delete](/api_help/main/reference/cuser/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

#### Смотрите также

* [Событие "OnSiteDelete"](/api_help/main/events/onsitedelete.php)
* [CSite::Delete](/api_help/main/reference/csite/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnBeforeSiteDelete"
	public static function OnBeforeSiteDeleteHandler($site_id)
	{
		// проверим есть ли связанные с удаляемым сайтом записи
		$strSql = "SELECT * FROM my_table WHERE SITE_ID=".$DB->ForSql($site_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
		// если связанные записи есть то
		if ($ar = $rs->Fetch()) 
		{
			// запретим удаление сайта
			global $APPLICATION;
			$APPLICATION->throwException("В моей таблице есть связанные записи.");
			return false;
		}
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeSiteDelete"
RegisterModuleDependences("main", "OnBeforeSiteDelete", 
	"my_module_id", "MyClass", "OnBeforeSiteDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: