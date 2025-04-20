[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskTags](/api_help/tasks/classes/ctasktags/index.php)

DeleteByName (10.0.5)

DeleteByName
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTags::DeleteByName(
	NAME
);Копировать
```

Метод удаляет теги с именем **NAME**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| NAME | Имя тега. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления связи, в противном случае возвращает **false**.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$NAME = "задача 2.0";
	if($USER->IsAdmin())
	{
		CTaskTags::DeleteByName($NAME);
	}
}
?>Копировать
```

Новинки документации в соцсетях: