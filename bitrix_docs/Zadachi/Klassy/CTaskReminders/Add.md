[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskReminders](/api_help/tasks/classes/ctaskreminders/index.php)

Add (10.0.6)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskReminders::Add(
	array arFields
);Копировать
```

Метод добавляет напоминание о задаче.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). |

#### Возвращаемое значение

Метод возвращает *true*, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TASK_ID" => 4,
		"USER_ID" => 15,
		"REMIND_DATE" => "2011-10-21",
		"TYPE" => CTaskReminders::REMINDER_TYPE_DEADLINE,
		"TRANSPORT" => CTaskReminders::REMINDER_TRANSPORT_EMAIL
	);
	$obTaskReminders = new CTaskReminders;
	$ID = $obTaskReminders->Add($arFields);
	$success = ($ID>0);
	if($success)
	{
		echo "Ok!";
	}
	else
	{
		if($e = $APPLICATION->GetException())
			echo "Error: ".$e->GetString();  
	}
}?>Копировать
```

Новинки документации в соцсетях: