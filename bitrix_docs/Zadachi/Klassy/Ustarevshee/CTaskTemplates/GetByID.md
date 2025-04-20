...

[Классы](/api_help/tasks/classes/index.php)

[Устаревшее](/api_help/tasks/classes/deprecated/index.php)

[CTaskTemplates](/api_help/tasks/classes/deprecated/ctasktemplates/index.php)

GetByID (10.0.4)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTasks::GetByID(
	ID,
	array arParams = array()
);Копировать
```

Возвращает поля шаблона по его идентификатору.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор шаблона. |  |
| arParams | Массив дополнительных параметров. Необязательный. | 12.5.8 |

#### Возвращаемое значение

Возвращается объект CDBResult.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$rsTemplate = CTaskTemplates::GetByID(104);
	if ($arTemplate = $rsTemplate->GetNext())
	{
		echo $arTemplate["TITLE"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: