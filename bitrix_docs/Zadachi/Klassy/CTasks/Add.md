[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

Add (10.0.2 - 12.0.9)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTasks::Add(
	array arFields,
	array arParams = array()
);Копировать
```

Метод добавляет новую задачу.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения всех полей задачи. Поля:  * **TITLE** - название задачи (можно искать по шаблону `[%_] ;)` ; * **DESCRIPTION** - описание задачи; * **DEADLINE** - крайний срок; * **START\_DATE\_PLAN** - плановая дата начала; * **END\_DATE\_PLAN** - плановая дата завершения; * **PRIORITY** - приоритет. Поле может принимать значения: [1] - Обычная [2] - Важная; * **ACCOMPLICES** - массив идентификаторов соисполнителей; * **AUDITORS** - массив идентификаторов наблюдателей; * **TAGS** - теги; * **ALLOW\_CHANGE\_DEADLINE** - флаг "Разрешить исполнителю (ответственному) менять крайний срок"; * **TASK\_CONTROL** - флаг "Принять работу после завершения задачи"; * **PARENT\_ID** - идентификатор родительской задачи; * **DEPENDS\_ON** - идентификатор предыдущей задачи; * **GROUP\_ID** - идентификатор рабочей группы; * **RESPONSIBLE\_ID** - идентификатор исполнителя (ответственного); * **TIME\_ESTIMATE** - плановые трудозатраты; * **CREATED\_BY** - идентификатор постановщика; * **DECLINE\_REASON** - причина отклонения задачи; * **STATUS** - мета-статус задачи; * **DURATION\_PLAN** - планируемая длительность в часах или днях; * **DURATION\_TYPE** - тип единицы измерения в планируемой длительности: days или hours; * **MARK** - оценка по задаче (возможные значения P (положительная) и N (отрицательная)); * **ALLOW\_TIME\_TRACKING** - флаг включения учета затраченного времени по задаче; * **ADD\_IN\_REPORT** - флаг включения задачи в отчет по эффективности; * **FORUM\_ID** - идентификатор форума, в котором хранятся комментарии к задаче; * **FORUM\_TOPIC\_ID** - идентификатор темы форума, в котором хранятся комментарии к задаче; * **SITE\_ID** - идентификатор сайта. По умолчанию в это поле записывается идентификатор сайта, на котором создается задача; * **MATCH\_WORK\_TIME** - флаг, который показывает, что даты исполнения и крайний срок должны всегда устанавливаться в рабочее время; |  |
| arParams | Массив дополнительных параметров. Необязательный. | 11.5.4 |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной задачи, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

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
	$obTask = new CTasks;
	$ID = $obTask->Add($arFields);
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

  

```
//Создание задачи с высоким приоритетом
{
	$arFields = Array("TITLE" => "High priority task",
		"DESCRIPTION" => "Task description",
		"RESPONSIBLE_ID" => 3,
		"CREATED_BY" => 1,
		"PRIORITY" => 2 // 2 соответствует высокому приоритету
	);
	$obTask = new CTasks;
	$obTask->Add($arFields);
}Копировать
```

Новинки документации в соцсетях: