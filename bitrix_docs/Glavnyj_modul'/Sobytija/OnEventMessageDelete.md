[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnEventMessageDelete (с версии 3.0.10)

OnEventMessageDelete
====================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
функция-обработчик(
	int template_id
);Копировать
```

Событие "OnEventMessageDelete" вызывается во время [удаления почтового шаблона](/api_help/main/reference/ceventmessage/delete.php). Как правило задачи обработчика данного события - очистить базу данных от записей связанных с удаляемым почтовым шаблоном.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *template\_id* | ID удаляемого почтового шаблона. |

#### Смотрите также

* [Событие "OnBeforeEventMessageDelete"](/api_help/main/events/onbeforeeventmessagedelete.php)
* [CEventMessage::Delete](/api_help/main/reference/ceventmessage/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnEventMessageDelete"
	public static function OnEventMessageDeleteHandler($template_id)
	{
		// удалим связанные записи
		$strSql = "DELETE FROM my_table WHERE TEMPLATE_ID=".intval($template_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnEventMessageDelete"
RegisterModuleDependences("main", "OnEventMessageDelete", 
	"my_module_id", "MyClass", "OnEventMessageDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: