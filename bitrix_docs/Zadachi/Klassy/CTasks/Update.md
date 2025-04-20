[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

Update (10.0.2 - 12.0.9)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTasks::Update(
	ID,
	array arFields
);Копировать
```

Метод изменяет параметры задачи с идентификатором ID.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемой задачи |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения всех полей задачи. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при возникновении ошибки метод вернет *false*. При возникновении ошибки в исключениях будет содержаться текст ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TITLE" => "New task title",
		"DESCRIPTION" => "New description"
	);
	$ID = 1;
	$obTask = new CTasks;
	$success = $obTask->Update($ID, $arFields);
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