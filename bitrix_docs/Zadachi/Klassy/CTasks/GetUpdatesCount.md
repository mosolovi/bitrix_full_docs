[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

GetUpdatesCount (С версии 10.0.5 - 12.0.9)

GetUpdatesCount
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CTasks::GetUpdatesCount(
	array arViewed
);Копировать
```

Возвращает количество изменений в задачах. 

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arViewed | Массив вида *array("идентификатор задачи"=>"дата, после которой считаются обновления" [, ...])*. |

#### Возвращаемое значение

Массив вида *array("идентификатор задачи"=>"количество обновлений" [, ...])*.

### Примеры использования

```
<?
$arViewed = array(
	193 => "26.01.2012 15:53:08",
	14 => "17.01.2012 17:24:58",
	99 => "13.01.2012 15:57:47",
	235 => "18.01.2012 14:34:35",
	3 => "28.12.2011 17:43:22"
);
$arUpdatesCount = CTasks::GetUpdatesCount($arViewed);
if ($arUpdatesCount)
{
	foreach($arUpdatesCount as $key=>$value)
	{
		echo "Updates count for task #".$key.": ".$value;
	}
}
?>Копировать
```

Новинки документации в соцсетях: