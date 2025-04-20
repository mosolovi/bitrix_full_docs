...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskDependence](/api_help/tasks/classes/deprecated/ctaskdependence/index.php)

Delete (10.0.5)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskDependence::Delete(
	TASK_ID,
	DEPENDS_ON_ID
);Копировать
```

Метод удаляет связь "задача" -> "предыдущая задача".

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| TASK\_ID | Идентификатор задачи. |
| DEPENDS\_ON\_ID | Идентификатор предыдущей задачи |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления связи, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$TASK_ID = 4;
	$DEPENDS_ON_ID = 15;
	if($USER->IsAdmin())
	{
		CTaskDependence::Delete($TASK_ID, $DEPENDS_ON_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: