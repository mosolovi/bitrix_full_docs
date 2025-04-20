[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskReminders](/api_help/tasks/classes/ctaskreminders/index.php)

DeleteByTaskID (10.0.6)

DeleteByTaskID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskReminders::DeleteByTaskID(
	TASK_ID
);Копировать
```

Метод удаляет напоминания о задаче с идентификатором **TASK\_ID**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

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
		CTaskReminders::DeleteByTaskID($TASK_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: