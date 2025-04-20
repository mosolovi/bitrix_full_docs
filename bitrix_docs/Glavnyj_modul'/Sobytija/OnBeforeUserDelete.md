[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeUserDelete (с версии 3.0.10)

OnBeforeUserDelete
==================

Включить вкладки

Описание и параметры

Пример

### Описание и параметры

```
bool
функция-обработчик(
	int user_id
);Копировать
```

Событие "OnBeforeUserDelete" вызывается перед [удалением пользователя](/api_help/main/reference/cuser/delete.php). Как правило задачи обработчика данного события - разрешить или запретить удаление пользователя.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *user\_id* | ID удаляемого пользователя. |

#### Возвращаемое значение

Для отмены удаления пользователя и прекращении выполнения метода [CUser::Delete](/api_help/main/reference/cuser/delete.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

#### Смотрите также

* [Событие "OnUserDelete"](/api_help/main/events/onuserdelete.php)
* [CUser::Delete](/api_help/main/reference/cuser/delete.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnBeforeUserDelete", Array("MyClass", "OnBeforeUserDeleteHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeUserDelete"
	public static function OnBeforeUserDeleteHandler($user_id)
	{
		// проверим есть ли связанные с удаляемым пользователем записи
		$strSql = "SELECT * FROM my_table WHERE USER_ID=".intval($user_id);
		$rs = $DB->Query($strSql, false, "FILE: ".__FILE__."<br>LINE: ".__LINE__);
		// если связанные записи есть то
		if ($ar = $rs->Fetch()) 
		{
			// запретим удаление пользователя
			global $APPLICATION;
			$APPLICATION->throwException("В моей таблице есть связанные записи.");
			return false;
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: