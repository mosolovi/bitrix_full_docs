[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyDelete (доступно с 3.3.2)

OnBeforeCurrencyDelete
======================

```
bool
функция-обработчик(
	string currency
);Копировать
```

OnBeforeCurrencyDelete - событие, вызываемое перед удалением валюты в методе [CCurrency::Delete](/api_help/currency/developer/ccurrency/ccurrency__delete.140a51ba.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |

#### Возвращаемое значение

* *true* - удаление разрешено;
* *false* - удаление отменено.

#### Смотрите также

* [CCurrency::Delete](/api_help/currency/developer/ccurrency/ccurrency__delete.140a51ba.php)

Новинки документации в соцсетях: