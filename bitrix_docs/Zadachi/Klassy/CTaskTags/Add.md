[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskTags](/api_help/tasks/classes/ctasktags/index.php)

Add (10.0.5)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTags::Add(
	array arFields
);Копировать
```

Метод добавляет теги к задаче.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит поля TASK\_ID - идентификатор задачи, USER\_ID - идентификатор пользователя и NAME - тег. |

#### Возвращаемое значение

Метод возвращает **true**, если добавление прошло успешно. При возникновении ошибки метод вернет **false**, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TASK_ID" => 4,
		"USER_ID" => 15,
		"NAME" => "задача 2.0",
	);
	$obTaskTags = new CTaskTags;
	$ID = $obTaskTags->Add($arFields);
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