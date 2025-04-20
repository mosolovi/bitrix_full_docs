[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskLog](/api_help/tasks/classes/ctasklog/index.php)

GetChanges (10.0.4)

GetChanges
==========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CTaskLog::GetChanges(
	array arOldValues,
	array arNewValues
);Копировать
```

Метод возвращает массив изменений на основе массива со старыми значениями и массива с измененными значениями.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arOldValues | Массив старых значений полей задачи. |
| arNewValues | Массив измененных значений полей задачи. |

#### Возвращаемое значение

Массив изменений.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$rsTask = CTasks::GetByID(2);
	if ($arTask = $rsTask->Fetch())
	{
		$arFields = array(
			"TITLE" => "New task title",
			"RESPONSIBLE_ID" => 45
		);
		$arChanges = CTaskLog::GetChanges($arTask, $arFields);
	}
}
?>Копировать
```

Новинки документации в соцсетях: