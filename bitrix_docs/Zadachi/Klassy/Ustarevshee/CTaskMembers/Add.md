...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskMembers](/api_help/tasks/classes/deprecated/ctaskmembers/index.php)

Add (10.0.5)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskMembers::Add(
	array arFields
);Копировать
```

Метод добавляет связь "задача -> пользователь".

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит поля:  * **TASK\_ID** - идентификатор задачи; * **USER\_ID** - идентификатор пользователя; * **TYPE** - тип (**A** - соисполнитель, **U** - наблюдатель). |

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
		"TYPE" => "U",
	);
	$obTaskMembers = new CTaskMembers;
	$ID = $obTaskMembers->Add($arFields);
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