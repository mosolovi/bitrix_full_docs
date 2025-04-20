[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnGroupDelete (с версии 3.0.10)

OnGroupDelete
=============

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int group_id
);Копировать
```

Событие "OnGroupDelete" вызывается в момент [удаления группы пользователей](/api_help/main/reference/cgroup/delete.php). Как правило задачи обработчика данного события - очистить базу данных от записей связанных с удаляемой группой пользователей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *group\_id* | ID удаляемой группы пользователей. |

#### Смотрите также

* [Событие "OnBeforeGroupDelete"](/api_help/main/events/onbeforegroupdelete.php)
* [CGroup::Delete](/api_help/main/reference/cgroup/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
AddEventHandler("main", "OnGroupDelete", Array("MyClass", "OnGroupDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnGroupDelete"
	public static function OnGroupDeleteHandler($group_id)
	{
		// удалим связанные записи
		$strSql = "DELETE FROM my_table WHERE GROUP_ID=".intval($group_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
	}
}
?>Копировать
```

Новинки документации в соцсетях: