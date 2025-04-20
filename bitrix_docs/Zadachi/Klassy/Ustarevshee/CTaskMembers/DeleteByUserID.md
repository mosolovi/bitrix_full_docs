...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskMembers](/api_help/tasks/classes/deprecated/ctaskmembers/index.php)

DeleteByUserID (10.0.5)

DeleteByUserID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskMembers::DeleteByUserID(
	USER_ID
);Копировать
```

Метод удаляет связь пользователя с идентификатором **USER\_ID** со всеми задачами.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| USER\_ID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления связи, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$USER_ID = 4;
	if($USER->IsAdmin())
	{
		CTaskMembers::DeleteByUserID($USER_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: