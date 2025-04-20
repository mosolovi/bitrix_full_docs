...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskTemplates](/api_help/tasks/classes/deprecated/ctasktemplates/index.php)

Update (10.0.4)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskTemplates::Update(
	ID,
	array arFields,
	array arParams = array()
);Копировать
```

Метод изменяет параметры шаблона с идентификатором ID.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор изменяемого шаблона. |  |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения всех полей шаблона. Обязательные поля должны быть заполнены. |  |
| arParams | Массив дополнительных параметров. Необязательный. | 12.5.0 |

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
	$obTemplate = new CTaskTemplates;
	$success = $obTemplate->Update($ID, $arFields);
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