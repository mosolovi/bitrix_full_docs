[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

Add

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CStatEvent::Add(
	int type_id,
	string event3,
	string date,
	string gid,
	mixed money = "",
	string currency = "",
	string chargeback = "N"
)Копировать
```

Добавляет [событие](/api_help/statistic/terms.php#event) по заданному [типу](/api_help/statistic/terms.php#event_type) и [специальному параметру](/api_help/statistic/terms.php#gid).

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *type\_id* | ID типа события. |
| *event3* | [Дополнительный параметр event3](/api_help/statistic/terms.php#event3) события. |
| *date* | Дата в [текущем формате](/api_help/main/general/constants.php#format_datetime). |
| *gid* | [Специальный параметр](/api_help/statistic/terms.php#gid) в котором закодированы все необходимые данные для добавления события. |
| *money* | Денежная сумма. |
| *currency* | Трехсимвольный идентификатор валюты. Идентификаторы валют задаются в модуле "Валюты". |
| *chargeback* | Флаг отрицательной суммы. Используется, когда необходимо зафиксировать событие о возврате денег (chargeback). Возможные значения:  * **Y** - денежная сумма отрицательная; * **N** - денежная сумма положительная. |

#### Возвращаемое значение

Функция возвращает ID добавленного события в случае успеха и 0 если событие не было добавлено по каким либо причинам.

### Смотрите также

* [CStatEvent::AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php)
* [CStatEvent::AddCurrent](/api_help/statistic/classes/cstatevent/addcurrent.php)
* [Загрузка событий](http://www.1c-bitrix.ru/user_help/statistic/events/event_edit.php)
* [Термин "Событие"](/api_help/statistic/terms.php#event)
* [Термин "Дополнительный параметр события (event3)"](/api_help/statistic/terms.php#event3)
* [Термин "Специальный параметр события"](/api_help/statistic/terms.php#gid)

### Примеры использования

```
<?
// добавим событие по типу события #1
// данный тип должен быть заранее создан
// специальный параметр события в незакодированном виде
$gid = "BITRIX_SM.995.82.N0.25.N.ru"; 
// дата должна быть заданы в формате текущего сайта или языка
$date = "23.12.2005 18:15:10";
CStatEvent::Add(1, "", $date, $gid, 99, "USD");
?>Копировать
```

```
<?
// добавим событие по типу события #2
// данный тип должен быть заранее создан
// специальный параметр события в закодированном виде
$gid = "BITRIX_SM.OTk1LjgyLk4wLjI1Lk4ucnU%3D";
// дата должна быть заданы в формате текущего сайта или языка
$date = "01.06.2005";
CStatEvent::Add(2, "", $date, $gid, "199", "EUR");
?>Копировать
```

Новинки документации в соцсетях: