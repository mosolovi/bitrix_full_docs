[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnCurrencyDelete (доступно с 3.3.2)

OnCurrencyDelete
================

```
функция-обработчик(
	string currency
);Копировать
```

OnCurrencyDelete - событие, вызываемое при удалении существующей валюты в методе [CCurrency::Delete](/api_help/currency/developer/ccurrency/ccurrency__delete.140a51ba.php). Может быть использовано для выполнения каких-либо действий при удалении валюты. Возвращаемое значение обработчика игнорируется.

#### Параметры

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |

#### Возвращаемое значение

Нет.

#### Смотрите также

* [CCurrency::Delete](/api_help/currency/developer/ccurrency/ccurrency__delete.140a51ba.php)

Новинки документации в соцсетях: