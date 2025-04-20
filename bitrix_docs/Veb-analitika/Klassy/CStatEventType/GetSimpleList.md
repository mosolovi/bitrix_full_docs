[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

GetSimpleList

GetSimpleList
=============

Включить вкладки

Описание и параметры

Смотрите также

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEventType::GetSimpleList(
	string &by = "s_event1",
	string &order = "desc",
	array filter = array(),
	bool &is_filtered
)Копировать
```

Возвращает список [типов событий](/api_help/statistic/terms.php#event_type) в упрощённом виде.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *by* | Поле для сортировки. Возможные значения:  * **s\_id** - ID типа события; * **s\_event1** - [идентификатор event1](/api_help/statistic/terms.php#event_type_id) типа события; * **s\_event2** - идентификатор event2 типа события; * **s\_name** - название типа события; * **s\_description** - описание типа события. |
| *оrder* | Порядок сортировки. Возможные значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации результирующего списка. В массиве допустимы следующие ключи:  * **ID**\* - ID типа события; * **ID\_EXACT\_MATCH** - если значение равно "N", то при фильтрации по **ID** будет искаться вхождение; * **EVENT1**\* - идентификатор event1 типа события; * **EVENT1\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **EVENT1** будет искаться точное совпадение; * **EVENT2**\* - идентификатор event2 типа события; * **EVENT2\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **EVENT2** будет искаться точное совпадение; * **NAME**\* - название типа события; * **NAME\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **NAME** будет искаться точное совпадение; * **DESCRIPTION**\* - описание типа события; * **DESCRIPTION\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **DESCRIPTION** будет искаться точное совпадение; * **KEYWORDS** - event1, event2, название и описание типа события; * **KEYWORDS\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **KEYWORDS** будет искаться точное совпадение.  \* - допускается [сложная логика](http://www.1c-bitrix.ru/user_help/general/filter.php) |
| *is\_filtered* | Флаг отфильтрованности результирующего списка. Если значение равно "true", то список был отфильтрован. |

### Смотрите также

* [CStatEventType::GetDynamicList](/api_help/statistic/classes/cstateventtype/getdynamiclist.php)
* [CStatEventType::GetList](/api_help/statistic/classes/cstateventtype/getlist.php)
* [Термин "Тип события"](/api_help/statistic/terms.php#event_type)

### Структура возвращаемой записи

```
Array
(
	[ID] => ID типа события
	[EVENT1] => идентификатор event1 типа события
	[EVENT2] => идентификатор event2 типа события
	[NAME] => название типа события
	[EVENT] => event1 / event2, либо название типа события если оно указано
	[DESCRIPTION] => описание типа события
)Копировать
```

### Примеры использования

```
<?
// выберем только те типы событий у которых в event1 входит "download"
$arFilter = array(
	"EVENT1" => "download"
);
// получим список записей
$rs = CStatEventType::GetSimpleList(
	($by="s_event2"), 
	($order="desc"), 
	$arFilter, 
	$is_filtered
);
// выведем все записи
while ($ar = $rs->Fetch())
{
	echo "<pre>"; print_r($ar); echo "</pre>";    
}
?>Копировать
```

Новинки документации в соцсетях: