[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedTime](/api_help/tasks/classes/ctaskelapsedtime/index.php)

Add (10.0.5)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTaskElapsedTime::Add(
	array arFields,
	array arParams = array()
);Копировать
```

Метод добавляет затраченное время к задаче.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). |  |
| arParams | Массив дополнительных параметров. Необязательный. | 12.5.3 |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной записи, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$arFields = array(
		"USER_ID" => 2,
		"TASK_ID" => 16,
		"MINUTES" => 90,
		"COMMENT_TEXT" => "Добавил полтора часа."
	);
	$obElapsed = new CTaskElapsedTime();
	$obElapsed->Add($arFields);
}?>Копировать
```

Новинки документации в соцсетях: