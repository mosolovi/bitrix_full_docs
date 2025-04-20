[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

GetByEvents

GetByEvents
===========

Включить вкладки

Описание и параметры

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEventType::GetByEvents(
	string event1,
	string event2
)Копировать
```

Возвращает [тип события](/api_help/statistic/terms.php#event_type) по указанным [идентификаторам](/api_help/statistic/terms.php#event_type_id).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event1* | Идентификатор event1 типа события. |
| *event2* | Идентификатор event2 типа события. |

#### Смотрите также

* [CStatEventType::ConditionSet](/api_help/statistic/classes/cstateventtype/conditionset.php)
* [Термин "Тип события"](/api_help/statistic/terms.php#event_type)

### Структура возвращаемой записи

```
Array
(
	[TYPE_ID] => ID типа события
	[DYNAMIC_KEEP_DAYS] => количество дней, отведенное для хранения статистики по данному типу события в разрезе по дням
	[KEEP_DAYS] => количество дней, отведенное для хранения событий данного типа
	[DATE_ENTER_STR] => дата создания события
)Копировать
```

### Примеры использования

```
<?
// зафиксируем событие типа "Скачивание файла manual.chm" (download/manual)
// если такого типа не существует, он будет автоматически создан
// событие будет фиксироваться по параметрам текущего посетителя сайта
// сначала проверим не скачивал ли уже текущий посетитель этот файл
// в течение последнего часа
// получим ID типа события
$rs = CStatEventType::GetByEvents($event1, $event2);
if ($ar = $rs->Fetch())
{
	// теперь получим все события данного типа для текущего посетителя сайта
	// произошедшие за последний час (3600 секунд)
	$rs = CStatEvent::GetListByGuest(
		$_SESSION["SESS_GUEST_ID"], 
		$ar["TYPE_ID"], "", 3600
	);
    
	// если таких событий не было...
	if (!($ar = $rs->Fetch()))
	{
		// ...добавляем данное событие
		CStatEvent::AddCurrent("download", "manual");
	}
}
?>Копировать
```

Новинки документации в соцсетях: