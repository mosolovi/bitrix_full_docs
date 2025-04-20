[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnUserDelete (с версии 3.0.10)

OnUserDelete
============

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
функция-обработчик(
	int user_id
)Копировать
```

Событие "OnUserDelete" вызывается в момент [удаления пользователя](/api_help/main/reference/cuser/delete.php). Как правило задачи обработчика данного события - очистить базу данных от записей связанных с удаляемым пользователем.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *user\_id* | ID удаляемого пользователя. |

#### Смотрите также

* [Событие "OnBeforeUserDelete"](/api_help/main/events/onbeforeuserdelete.php)
* [CUser::Delete](/api_help/main/reference/cuser/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/modules/my_module_id/include.php
class MyClass
{
	// создаем обработчик события "OnUserDelete"
	public static function OnUserDeleteHandler($user_id)
	{
		// удалим связанные записи
		global $DB;
		$strSql = "DELETE FROM my_table WHERE USER_ID=".intval($user_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnUserDelete"
RegisterModuleDependences("main", "OnUserDelete", 
	"my_module_id", "MyClass", "OnUserDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: