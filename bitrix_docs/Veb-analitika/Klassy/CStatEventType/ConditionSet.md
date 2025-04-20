[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEventType](/api_help/statistic/classes/cstateventtype/index.php)

ConditionSet

ConditionSet
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CStatEventType::ConditionSet(
	string event1,
	string event2,
	array &type
)Копировать
```

Находит [тип события](/api_help/statistic/terms.php#event_type) по указанным [идентификаторам](/api_help/statistic/terms.php#event_type_id), либо создает новый тип события если такого ещё не существует.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event1* | Идентификатор event1 типа события. |
| *event2* | Идентификатор event2 типа события. |
| *type* | Ссылка на массив описывающий найденный, либо созданный тип события. Структура данного массива:  ``` Array ( 	[TYPE_ID] => ID типа события 	[DYNAMIC_KEEP_DAYS] => количество дней, отведенное для хранения статистики по данному типу события в разрезе по дням 	[KEEP_DAYS] => количество дней, отведенное для хранения событий данного типа 	[DATE_ENTER_STR] => дата создания события )Копировать ``` |

#### Возвращаемое значение

Метод возвращает ID найденного типа события, либо вновь созданного.

### Смотрите также

* [CStatEventType::GetByEvents](/api_help/statistic/classes/cstateventtype/getbyevents.php)
* [CStatEventType::GetByID](/api_help/statistic/classes/cstateventtype/getbyid.php)
* [Термин "Тип события"](/api_help/statistic/terms.php#event_type)

### Примеры использования

```
<?
// получим ID типа события "softkey/order"
// либо создадим новый тип события
$TYPE_ID = CStatEventType::ConditionSet("softkey", "order", $arEventType);
?>Копировать
```

Новинки документации в соцсетях: