[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyRateDelete (доступно с 14.0.0)

OnBeforeCurrencyRateDelete
==========================

```
bool функция-обработчик(
	int ID
);Копировать
```

OnBeforeCurrencyRateDelete - событие, вызываемое перед удалением курса валюты в методе [CCurrencyRates::Delete](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__delete.28de3643.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Код курса валюты. |

#### Возвращаемое значение

* *true* - удаление разрешено;
* *false* - удаление отменено.

#### Смотрите также

* [CCurrencyRates::Delete](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__delete.28de3643.php)

Новинки документации в соцсетях: