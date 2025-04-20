[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

GetByID

GetByID
=======

Включить вкладки

Описание и параметры

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEventType::GetByID(
	int type_id
)Копировать
```

Возвращает данные по указанному [типу события](/api_help/statistic/terms.php#event_type).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *type\_id* | ID типа события. |

#### Смотрите также

* [CStatEventType::GetByEvents](/api_help/statistic/classes/cstateventtype/getbyevents.php)
* [CStatEventType::ConditionSet](/api_help/statistic/classes/cstateventtype/conditionset.php)
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
	[MONEY] => суммарная денежная сумма по данному типу события
	[DATE_ENTER] => дата создания типа события
	[DATE_CLEANUP] => дата очистки статистики по данному типу события в разрезе по дням
	[C_SORT] => порядок сортировки
	[COUNTER] => счетчик хранящий часть суммарного количества событий данного типа
	[ADV_VISIBLE] => [Y|N] флаг: включать ли статистику по данному типу события в отчет по рекламным кампаниям
	[KEEP_DAYS] => количество дней отведенное для хранения событий данного типа
	[DYNAMIC_KEEP_DAYS] => количество дней, отведенное для хранения статистики по данному типу события в разрезе по дням
	[DIAGRAM_DEFAULT] => [Y|N] флаг: включать ли данный тип события в круговую диаграмму и график по умолчанию
)Копировать
```

### Примеры использования

```
<?
$type_id = 1;
if ($rs = CStatEventType::GetByID($type_id))
{
	$ar = $rs->Fetch();
	// выведем параметры типа события
	echo "<pre>"; print_r($ar); echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях: