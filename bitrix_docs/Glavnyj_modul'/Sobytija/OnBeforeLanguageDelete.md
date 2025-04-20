[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeLanguageDelete (с версии 3.3.21)

OnBeforeLanguageDelete
======================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
bool
функция-обработчик(
	string language_id
);Копировать
```

Событие "OnBeforeLanguageDelete" вызывается перед [удалением языка](/api_help/main/reference/clanguage/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление языка.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *language\_id* | ID удаляемого языка. |

#### Возвращаемое значение

Для отмены удаления языка и прекращении выполнения метода [CLanguage::Delete](/api_help/main/reference/clanguage/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.   

#### Смотрите также

* [Событие "OnLanguageDelete"](/api_help/main/events/onlanguagedelete.php)
* [CLanguage::Delete](/api_help/main/reference/clanguage/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnBeforeLanguageDelete"
	public static function OnBeforeLanguageDeleteHandler($language_id)
	{
		// проверим есть ли связанные с удаляемым языком записи
		$strSql = "SELECT * FROM my_table WHERE LANGUAGE_ID=".$DB->ForSql($language_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
		// если связанные записи есть то
		if ($ar = $rs->Fetch()) 
		{
			// запретим удаление языка
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
// регистрируем обработчик события "OnBeforeLanguageDelete"
RegisterModuleDependences("main", "OnBeforeLanguageDelete", 
	"my_module_id", "MyClass", "OnBeforeLanguageDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: