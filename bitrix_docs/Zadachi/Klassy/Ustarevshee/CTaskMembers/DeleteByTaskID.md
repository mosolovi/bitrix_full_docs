...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskMembers](/api_help/tasks/classes/deprecated/ctaskmembers/index.php)

DeleteByTaskID (10.0.5)

DeleteByTaskID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskMembers::DeleteByTaskID(
	TASK_ID,
	TYPE = null
);Копировать
```

Метод удаляет связь задачи с идентификатором **TASK\_ID** со всеми пользователями.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| TASK\_ID | Идентификатор задачи. |
| *TYPE* | Тип пользователя (**A** - соисполнитель, **U** - наблюдатель). Необязательный. По умолчанию будут удалены связи с пользователями всех типов. |

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
		CTaskMembers::DeleteByTaskID($TASK_ID, "U");
	}
}
?>Копировать
```

Новинки документации в соцсетях: