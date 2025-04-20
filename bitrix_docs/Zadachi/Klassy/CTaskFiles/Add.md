[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFiles](/api_help/tasks/classes/ctaskfiles/index.php)

Add (10.0.5, устарел с версии 16.7.0)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskFiles::Add(
	array arFields,
	array arParams = array()
);Копировать
```

Метод добавляет связь "задача -> файл".

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит поля:  * **TASK\_ID** - идентификатор задачи; * **FILE\_ID** - идентификатор файла. |  |
| arParams | Массив дополнительных параметров. Необязательный. | 12.5.0 |

#### Возвращаемое значение

Метод возвращает *true*, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = Array(
		"TASK_ID" => 4,
		"FILE_ID" => 15
	);
	$obTaskFiles = new CTaskFiles;
	$ID = $obTaskFiles->Add($arFields);
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