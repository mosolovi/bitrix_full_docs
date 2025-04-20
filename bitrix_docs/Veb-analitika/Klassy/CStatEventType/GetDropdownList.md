[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

GetDropdownList

GetDropdownList
===============

Включить вкладки

Описание и параметры

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEventType::GetDropdownList(
	string order = "ORDER BY EVENT1, EVENT2"
)Копировать
```

Возвращает список [типов событий](/api_help/statistic/terms.php#event_type) для вывода его в выпадающем списке с помощью функции [SelectBox](/api_help/main/functions/html/selectbox.php), либо в списке множественного выбора с помощью функции [SelectBoxM](/api_help/main/functions/html/selectboxm.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *order* | SQL код, позволяющий задать произвольную сортировку списка типов событий. |

#### Смотрите также

* [CStatEventType::GetList](/api_help/statistic/classes/cstateventtype/getlist.php)
* [CStatEventType::GetSimpleList](/api_help/statistic/classes/cstateventtype/getsimplelist.php)
* [Термин "Тип события"](/api_help/statistic/terms.php#event_type)

### Структура возвращаемой записи

```
Array
(
	[REFERENCE_ID] => ID типа событий
	[REFERENCE] => "[ID] (event1 / event2) название типа события"
)Копировать
```

### Примеры использования

```
<?
// выпадающий список с одиночным выбором
echo SelectBox(
	"SEARCHER_ID", 
	CStatEventType::GetDropdownList(), 
	"", 
	intval($SEARCHER_ID)
);
// список из 20 видимых элементов с возможностью множественного выбора
echo SelectBoxM(
	"arSEARCHER_ID[]", 
	CStatEventType::GetDropdownList(), 
	$arSEARCHER_ID, 
	"", 
	false, 
	20
);
?>Копировать
```

Новинки документации в соцсетях: