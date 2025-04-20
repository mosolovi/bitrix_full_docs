[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

AddCurrent

AddCurrent
==========

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
array
CStatEvent::AddCurrent(
	string event1,
	string event2 = "",
	string event3 = "",
	mixed money = "",
	string currency = "",
	string goto = "",
	string chargeback = "N",
	mixed site_id = false
)Копировать
```

Добавляет [событие](/api_help/statistic/terms.php#event) используя текущие параметры [посетителя](/api_help/statistic/terms.php#guest). Если [типа события](/api_help/statistic/terms.php#event_type) с [идентификаторами](/api_help/statistic/terms.php#event_type_id) *event1*, *event2* не существует, то он будет автоматически создан с указанными идентификаторами.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *event1* | Идентификатор типа события event1. |
| *event2* | Идентификатор типа события event2. |
| *event3* | [Дополнительный параметр event3](/api_help/statistic/terms.php#event3) события. |
| *money* | Денежная сумма. |
| *currency* | Трехсимвольный идентификатор валюты. Идентификаторы валют задаются в модуле "Валюты". |
| *goto* | Адрес страницы куда перешел посетитель. Как правило используется в скриптах вида /bitrix/redirect.php, перенаправляющих посетителей на другие страницы с одновременной фиксацией события. |
| *chargeback* | Флаг отрицательной суммы. Используется когда необходимо зафиксировать событие о возврате денег (chargeback). Возможные значения:  * **Y** - денежная сумма отрицательная; * **N** - денежная сумма положительная. |
| *site\_id* | ID сайта к которому будет привязано будущее событие. |

### Возвращаемое значение

Метод возвращает массив вида:

```
Array
(
	[TYPE_ID] => ID типа события
	[EID] => ID добавленного события
)Копировать
```

### Смотрите также

* [CStatEvent::Add](/api_help/statistic/classes/cstatevent/add.php)
* [CStatEvent::AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php)
* [Термин "Событие"](/api_help/statistic/terms.php#event)
* [Термин "Дополнительный параметр события (event3)"](/api_help/statistic/terms.php#event3)

### Примеры использования

```
<?
// зафиксируем событие типа "Просмотр спец. страницы" (view/special_page)
CStatEvent::AddCurrent("softkey", "out", $GLOBALS["APPLICATION"]->GetCurPage());
?>Копировать
```

```
<?
// зафиксируем событие типа "Уход на оплату заказа на Софткее" (softkey/out)
// если такого типа не существует, то он будет автоматически создан
// событие будет фиксироваться по параметрам текущего посетителя сайта
// в данной переменной может быть задана страница на которую осуществляется переход
$goto = "http://www.softkey.ru/catalog/basket.php?prodid=902&quantity=1&referer1=ritlabs_site&referer2=BITRIX_SM.OTk1LjgyLk4wLjI1Lk4ucnU%3D";
CStatEvent::AddCurrent("softkey", "out", "", "", "", $goto);
?>Копировать
```

```
<?
// зафиксируем событие типа "Скачивание файла manual.chm" (download/manual)
// если такого типа не существует, то он будет автоматически создан
// событие будет фиксироваться по параметрам текущего посетителя сайта
// сначала проверим не скачивал ли уже текущий посетитель этот файл
// в течение последнего часа
// получим ID типа события
$rs = CStatEventType::GetByEvents($event1, $event2);
if ($ar = $rs->Fetch())
{
	// теперь получим все события данного типа для текущего посетителя сайта
	// произошедшие за последний час (3600 секунд)
	$rs = CStatEvent::GetListByGuest($_SESSION["SESS_GUEST_ID"], $ar["TYPE_ID"], "", 3600);
    
	// если таких событий не было то
	if (!($ar=$rs->Fetch()))
	{
		// добавляем данное событие
		CStatEvent::AddCurrent("download", "manual");
	}
}
?>Копировать
```

Новинки документации в соцсетях: