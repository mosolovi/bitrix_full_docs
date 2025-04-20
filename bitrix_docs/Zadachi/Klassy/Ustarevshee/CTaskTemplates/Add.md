...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskTemplates](/api_help/tasks/classes/deprecated/ctasktemplates/index.php)

Add (10.0.4)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTaskTemplates::Add(
	array arFields,
	array arParams = array()
);Копировать
```

Метод добавляет новый шаблон.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения всех полей шаблона. |  |
| arParams | Массив дополнительных параметров. Необязательный. | 12.5.0 |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного шаблона, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TITLE" => "Task title",
		"DESCRIPTION" => "Task description",
		"RESPONSIBLE_ID" => 2,
		"GROUP_ID" => 3
	);
	$obTemplate = new CTaskTemplates;
	$ID = $obTemplate->Add($arFields);
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