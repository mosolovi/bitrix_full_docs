[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedTime](/api_help/tasks/classes/ctaskelapsedtime/index.php)

GetByID (10.0.5)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTaskElapsedTime::GetByID(
	ID
);Копировать
```

Возвращает поля записи о затраченном времени по ее идентификатору.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор записи. |

#### Возвращаемое значение

Возвращается объект CDBResult.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$rsElapsedTime = CTaskElapsedTime::GetByID(18);
	if ($arElapsedTime = $rsElapsedTime->GetNext())
	{
		echo $arElapsedTime["MINUTES"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: