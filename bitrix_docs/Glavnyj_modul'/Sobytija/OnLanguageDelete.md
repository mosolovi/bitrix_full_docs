[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnLanguageDelete (с версии 3.3.21)

OnLanguageDelete
================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
функция-обработчик(
	int language_id
);Копировать
```

Событие "OnLanguageDelete" вызывается во время [удаления языка](/api_help/main/reference/clanguage/delete.php). Как правило задачи обработчика данного события - очистить базу данных от записей связанных с удаляемым языком.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *language\_id* | ID удаляемого языка. |

#### Смотрите также

* [Событие "OnBeforeLanguageDelete"](/api_help/main/events/onbeforelanguagedelete.php)
* [CLanguage::Delete](/api_help/main/reference/clanguage/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnLanguageDelete"
	public static function OnLanguageDeleteHandler($language_id)
	{
		// удалим связанные записи
		$strSql = "DELETE FROM my_table WHERE LANGUAGE_ID=".$DB->ForSql($language_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnLanguageDelete"
RegisterModuleDependences("main", "OnLanguageDelete", 
	"my_module_id", "MyClass", "OnLanguageDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: