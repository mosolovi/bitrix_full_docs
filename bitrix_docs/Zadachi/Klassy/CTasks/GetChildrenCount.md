[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

GetChildrenCount (10.0.2 - 12.0.9)

GetChildrenCount
================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTasks::е(
	array arFilter,
	array arParentIDs
);Копировать
```

Возвращает количество подзадач по фильтру **arFilter** для задач **arParentIDs**. 

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. |
| arParentIDs | Массив идентификаторов задач, для которых выбирается количество подзадач. |

#### Возвращаемое значение

Возвращается объект [CDBResult](http://dev.1c-bitrix.ru/api_help/main/reference/cdbresult/index.php "CDBResult").

### Примеры использования

```
<?
$arFilter = array(
	"RESPONSIBLE_ID" => 2
);
$arTasksIDs = array(193, 14, 99, 235, 3);
$rsChildrenCount = CTasks::GetChildrenCount($arFilter, $arTasksIDs);
if ($rsChildrenCount)
{
	while($arChildrenCount = $rsChildrenCount->Fetch())
	{
		echo "Children count for task #".$arChildrenCount["PARENT_ID"].": ".$arChildrenCount["CNT"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: