[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeGroupDelete (с версии 3.0.10)

OnBeforeGroupDelete
===================

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
bool
функция-обработчик(
	int group_id
);Копировать
```

Событие "OnBeforeGroupDelete" вызывается перед [удалением группы пользователей](/api_help/main/reference/cgroup/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление группы пользователей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *group\_id* | ID удаляемой группы пользователей. |

#### Возвращаемое значение

Для отмены удаления пользователя и прекращении выполнения метода [CGroup::Delete](/api_help/main/reference/cgroup/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

#### Смотрите также

* [Событие "OnGroupDelete"](/api_help/main/events/ongroupdelete.php)
* [CGroup::Delete](/api_help/main/reference/cgroup/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeGroupDelete", Array("MyClass", "OnBeforeGroupDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeGroupDelete"
	public static function OnBeforeGroupDeleteHandler($group_id)
	{
		// проверим есть ли связанные с удаляемой группой пользователей записи
		$strSql = "SELECT * FROM my_table WHERE GROUP_ID=".intval($group_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
		// если связанные записи есть то
		if ($ar = $rs->Fetch()) 
		{
			// запретим удаление группы пользователей
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
// регистрируем обработчик события "OnBeforeGroupDelete" для модуля my_module_id
RegisterModuleDependences("main", "OnBeforeGroupDelete", 
	"my_module_id", "MyClass", "OnBeforeGroupDeleteHandler");
?>Копировать
```

Новинки документации в соцсетях: