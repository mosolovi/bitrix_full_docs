[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

GetDynamicList

GetDynamicList
==============

Включить вкладки

Описание и параметры

Смотрите также

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEventType::GetDynamicList(
	int type_id,
	string &by = "s_date",
	string &order = "desc",
	array max_min,
	array filter
)Копировать
```

Возвращает количество [событий](/api_help/statistic/terms.php#event) указанного [типа](/api_help/statistic/terms.php#event_type) в разрезе по дням.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *type\_id* | ID типа события. |
| *by* | Поле для сортировки. Возможные значения:  * **s\_date** - дата. |
| *оrder* | Порядок сортировки. Возможные значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *max\_min* | Ссылка на массив содержащий максимальную и минимальную даты результирующего списка. Структура данного массива:  ``` Array ( 	[DATE_FIRST] => минимальная дата 	[MIN_DAY] => день минимальной даты (1-31) 	[MIN_MONTH] => месяц минимальной даты (1-12) 	[MIN_YEAR] => год минимальной даты 	[DATE_LAST] => максимальная дата 	[MAX_DAY] => день максимальной даты (1-31) 	[MAX_MONTH] => месяц максимальной даты (1-12) 	[MAX_YEAR] => год максимальной даты  )Копировать ``` |
| *filter* | Массив для фильтрации результирующего списка. В массиве допустимы следующие ключи:  * **DATE1** - начальное значение интервала для поля "дата"; * **DATE2** - конечное значение интервала для поля "дата". |

### Смотрите также

* [CStatEventType::GetList](/api_help/statistic/classes/cstateventtype/getlist.php)
* [CStatEventType::GetSimpleList](/api_help/statistic/classes/cstateventtype/getsimplelist.php)

### Структура возвращаемой записи

```
Array
(
	[DATE_STAT] => дата
	[DAY] => день (1-31)
	[MONTH] => месяц (1-12)
	[YEAR] => год
	[COUNTER] => количество событий указанного типа для данной даты
)Копировать
```

### Примеры использования

```
<?
$type_id = 1;
// установим фильтр на декабрь 2007 года
$arFilter = array(
	"DATE1" => "01.12.2007",
	"DATE2" => "31.12.2007"
);
// получим набор записей
$rs = CStatEventType::GetDynamicList(
	$type_id, 
	($by="s_date"), 
	($order="desc"), 
	$arMaxMin, 
	$arFilter
);
// выведем массив с максимальной и минимальной датами
echo "<pre>"; print_r($arMaxMin); echo "</pre>";    
// выведем все записи
while ($ar = $rs->Fetch())
{
	echo "<pre>"; print_r($ar); echo "</pre>";    
}
?>Копировать
```

Новинки документации в соцсетях: