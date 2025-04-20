[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeEventMessageDelete (с версии 3.0.10)

OnBeforeEventMessageDelete
==========================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
bool
функция-обработчик(
	int template_id
);Копировать
```

Событие "OnBeforeEventMessageDelete" вызывается перед [удалением почтового шаблона](/api_help/main/reference/ceventmessage/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление почтового шаблона.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *template\_id* | ID удаляемого почтового шаблона. |

#### Возвращаемое значение

Для отмены удаления пользователя и прекращении выполнения метода [CEventMessage::Delete](/api_help/main/reference/ceventmessage/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

#### Смотрите также

* [Событие "OnEventMessageDelete"](/api_help/main/events/oneventmessagedelete.php)
* [CEventMessage::Delete](/api_help/main/reference/ceventmessage/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnBeforeEventMessageDelete"
	public static function OnBeforeEventMessageDeleteHandler($template_id)
	{
		// проверим есть ли связанные с удаляемым шаблоном записи
		$strSql = "SELECT * FROM my_table WHERE EMAIL_TEMPLATE_ID=".intval($template_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
		// если связанные записи есть то
		if ($ar = $rs->Fetch()) 
		{
			// запретим удаление почтового шаблона
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
// регистрируем обработчик события "OnBeforeEventMessageDelete"
RegisterModuleDependences("main", "OnBeforeEventMessageDelete", 
	"my_module_id", "MyClass", "OnBeforeEventMessageDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: