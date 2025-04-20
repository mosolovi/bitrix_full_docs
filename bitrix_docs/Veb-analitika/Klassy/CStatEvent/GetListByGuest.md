[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

GetListByGuest

GetListByGuest
==============

Включить вкладки

Описание и параметры

Смотрите также

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CStatEvent::GetListByGuest(
	int guest_id,
	mixed type_id = false,
	mixed event3 = false,
	mixed time = false
)Копировать
```

Возвращает список идентификаторов [событий](/api_help/statistic/terms.php#event) по указанному ID [посетителя](/api_help/statistic/terms.php#guest) сайта.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *guest\_id* | ID посетителя. |
| *type\_id* | ID типа события. Если значение равно "false", то фильтрации по типу события не будет. |
| *event3* | [Дополнительный параметр event3](/api_help/statistic/terms.php#event3) события. Если значение равно "false", то фильтрации по event3 не будет. |
| *time* | Количество секунд, прошедших с текущего момента. Если значение равно "false", то фильтрации по времени не будет. |

### Смотрите также

* [CStatEvent::GetList](/api_help/statistic/classes/cstatevent/getlist.php)
* [Термин "Событие"](/api_help/statistic/terms.php#event)
* [Термин "Дополнительный параметр события (event3)"](/api_help/statistic/terms.php#event3)

### Структура возвращаемой записи

```
Array
(
	[ID] => ID события
)Копировать
```

### Примеры использования

```
<?
// зафиксируем событие типа
// "Скачивание файла manual.chm" (download/manual)
// если такого типа не существует, он будет автоматически создан
// событие будет фиксироваться по параметрам
// текущего посетителя сайта
// сначала проверим - не скачивал ли уже текущий посетитель
// этот файл в течение последнего часа
// получим ID типа события
$rs = CStatEventType::GetByEvents($event1, $event2);
if ($ar = $rs->Fetch())
{
	// теперь получим все события данного типа
	// для текущего посетителя сайта,
	// произошедшие за последний час (3600 секунд)
	$rs = CStatEvent::GetListByGuest(
		$_SESSION["SESS_GUEST_ID"], 
		$ar["TYPE_ID"], "", 3600
	);
    
	// если таких событий не было...
	if (!($ar=$rs->Fetch()))
	{
		// ...добавляем данное событие
		CStatEvent::AddCurrent("download", "manual");
	}
}
?>Копировать
```

Новинки документации в соцсетях: