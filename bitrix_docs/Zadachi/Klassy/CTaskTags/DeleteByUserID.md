[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskTags](/api_help/tasks/classes/ctasktags/index.php)

DeleteByUserID (10.0.5)

DeleteByUserID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTags::DeleteByUserID(
	USER_ID
);Копировать
```

Метод удаляет теги пользователя с идентификатором **USER\_ID**.

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
		CTaskTags::DeleteByUserID($USER_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: