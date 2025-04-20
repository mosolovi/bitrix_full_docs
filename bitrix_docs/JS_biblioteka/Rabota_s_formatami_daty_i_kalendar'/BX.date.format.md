[JS библиотека](/api_help/js_lib/index.php)

[Работа с форматами даты и календарь](/api_help/js_lib/data/index.php)

BX.date.format

BX.date.format
==============

```
String 
BX.date.format(
	String format,
	Number|Date timestamp,
	Number|Date now,
	Boolean utc
);Копировать
```

Перенос в JavaScript функции [FormatDate](/api_help/main/functions/date/formatdate.php).

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| **format** | Описание формата даты |
| **timestamp** | Дата-время в виде UNIX timestamp или объекта Date. Тип данных Date | Number |
| **now** | Текущие дата-время в виде UNIX timestamp или объекта Date (нужно для некоторых вариантов полей формата, опирающихся на текущее время). |
| **utc** | Флаг "переданы даты в UTC" |

Новинки документации в соцсетях: