[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockFormatProperties](/api_help/iblock/classes/ciblockformatproperties/index.php)

DateFormat (доступен с 5.9.0)

DateFormat
==========

```
string CIBlockFormatProperties::DateFormat(
	string format, 
	string timestamp
) Копировать
```

Конвертирует дату в нужный формат. Доступные форматы можно посмотреть, вызвав **CIBlockParameters::GetDateFormat**. Метод статический.

**Примечание:** является функцией-оберткой для [FormatDate](/api_help/main/functions/date/formatdate.php).

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| format | Формат даты/времени. Может дополнительно принимать 2 значения: *SHORT* и *FULL* (для них берется формат даты или времени для сайта). |
| timestamp | Метка времени в Unix формате. |

#### Возвращаемое значение

Отформатированная строка.

Новинки документации в соцсетях: