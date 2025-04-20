...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskDependence](/api_help/tasks/classes/deprecated/ctaskdependence/index.php)

Add (10.0.5)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskDependence::Add(
	array arFields
);Копировать
```

Метод добавляет к задаче предыдущую.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит поля:  * **TASK\_ID** - идентификатор задачи; * **DEPENDS\_ON\_ID** - идентификатор предыдущей задачи. |

#### Возвращаемое значение

Метод возвращает *true*, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TASK_ID" => 4,
		"DEPENDS_ON_ID" => 15
	);
	$obTaskDependence = new CTaskDependence;
	$ID = $obTaskDependence->Add($arFields);
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