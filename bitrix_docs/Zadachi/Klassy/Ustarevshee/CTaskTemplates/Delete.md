...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskTemplates](/api_help/tasks/classes/deprecated/ctasktemplates/index.php)

Delete (10.0.4)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTemplates::Delete(
	ID
);Копировать
```

Метод удаляет шаблон с идентификатором ID.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор удаляемого шаблона |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления шаблона, в противном случае возвращает false.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	if($USER->IsAdmin())
	{
		CTaskTemplates::Delete($ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: