[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskTags](/api_help/tasks/classes/ctasktags/index.php)

DeleteByTaskID (10.0.5)

DeleteByTaskID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTags::DeleteByTaskID(
	TASK_ID
);Копировать
```

Метод удаляет теги задачи с идентификатором **TASK\_ID**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| TASK\_ID | Идентификатор задачи. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления связи, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$TASK_ID = 15;
	if($USER->IsAdmin())
	{
		CTaskTags::DeleteByTaskID($TASK_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: