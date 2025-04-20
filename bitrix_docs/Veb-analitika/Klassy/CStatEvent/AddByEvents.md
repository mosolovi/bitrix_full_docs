[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

AddByEvents

AddByEvents
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CStatEvent::AddByEvents(
	string event1,
	string event2,
	string event3,
	string date,
	string gid,
	mixed money = "",
	string currency = "",
	string chargeback = "N"
)Копировать
```

Добавляет [событие](/api_help/statistic/terms.php#event) по заданным [идентификаторам](/api_help/statistic/terms.php#event_type_id) [типа события](/api_help/statistic/terms.php#event_type) и [специальному параметру](/api_help/statistic/terms.php#gid). Если [типа события](/api_help/statistic/terms.php#event_type) с идентификаторами *event1*, *event2* не существует, то он будет автоматически создан с указанными идентификаторами.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event1* | Идентификатор типа события event1. |
| *event2* | Идентификатор типа события event2. |
| *event3* | [Дополнительный параметр event3](/api_help/statistic/terms.php#event3) события. |
| *date* | Дата в [текущем формате](/api_help/main/general/constants.php#format_datetime). |
| *gid* | [Специальный параметр](/api_help/statistic/terms.php#gid) в котором закодированы все необходимые данные для добавления события. |
| *money* | Денежная сумма. |
| *currency* | Трехсимвольный идентификатор валюты. Идентификаторы валют задаются в модуле "Валюты". |
| *chargeback* | Флаг отрицательной суммы. Используется когда необходимо зафиксировать событие о возврате денег (chargeback). Возможные значения:  * **Y** - денежная сумма отрицательная; * **N** - денежная сумма положительная. |

#### Возвращаемое значение

Метод возвращает ID добавленного события в случае успеха, и 0, если событие не было добавлено по каким либо причинам.

### Смотрите также

* [CStatEvent::Add](/api_help/statistic/classes/cstatevent/add.php)
* [CStatEvent::AddCurrent](/api_help/statistic/classes/cstatevent/addcurrent.php)
* [Загрузка событий](http://www.1c-bitrix.ru/user_help/statistic/events/event_edit.php)
* [Термин "Событие"](/api_help/statistic/terms.php#event)
* [Термин "Дополнительный параметр события (event3)"](/api_help/statistic/terms.php#event3)
* [Термин "Специальный параметр события"](/api_help/statistic/terms.php#gid)

### Примеры использования

```
<?
// добавим событие по типу softkey/buy
// если такого типа нет, то он автоматически будет создан
// специальный параметр события в незакодированном виде
$gid = "BITRIX_SM.995.82.N0.25.N.ru";
// дата должна быть заданы в формате текущего сайта или языка
$date = "23.12.2005 18:15:10";
CStatEvent::AddByEvents("softkey", "buy", "", $date, $gid, "899", "USD");
?>
Копировать
```

```
<?
// добавим событие по типу regnow/buy
// если такого типа нет, то он автоматически будет создан
// специальный параметр события в закодированном виде
$gid = "BITRIX_SM.OTk1LjgyLk4wLjI1Lk4ucnU%3D";
// дата должна быть заданы в формате текущего сайта или языка
$date = "01.06.2005";
CStatEvent::AddByEvents("regnow", "buy", "", $date, $gid, "199", "EUR");
?>Копировать
```

Новинки документации в соцсетях: