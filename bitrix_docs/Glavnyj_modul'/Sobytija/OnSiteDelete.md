[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnSiteDelete (с версии 4.0.6)

OnSiteDelete
============

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
функция-обработчик(
	int site_id
);Копировать
```

Событие "OnSiteDelete" вызывается во время [удаления сайта](/api_help/main/reference/csite/delete.php). Как правило задачи обработчика данного события - очистить базу данных от записей связанных с удаляемым сайтом.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *site\_id* | ID удаляемого сайта. |

#### Смотрите также

* [Событие "OnBeforeSiteDelete"](/api_help/main/events/onbeforesitedelete.php)
* [CSite::Delete](/api_help/main/reference/csite/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnSiteDelete"
	public static function OnSiteDeleteHandler($site_id)
	{
		// удалим связанные записи
		$strSql = "DELETE FROM my_table WHERE SITE_ID=".$DB->ForSql($site_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnSiteDelete"
RegisterModuleDependences("main", "OnSiteDelete", 
	"my_module_id", "MyClass", "OnSiteDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: