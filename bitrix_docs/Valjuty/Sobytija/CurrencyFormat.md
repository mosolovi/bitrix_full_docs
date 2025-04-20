[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

CurrencyFormat (доступно с 8.0.2)

CurrencyFormat
==============

```
string функция-обработчик(
	float price,
	string currency
);Копировать
```

CurrencyFormat - событие, вызываемое при форматировании цены в соответствии с настройками валюты.

#### Параметры

| Параметр | Описание |
| --- | --- |
| price | Цена (денежная сумма), которую нужно отформатировать. |
| currency | Валюта, по правилам которой нужно производить форматирование. |

#### Возвращаемое значение

Если обработчик возвращает непустую строку, то она будет возвращена и как результат работы метода [CCurrencyLang::CurrencyFormat](/api_help/currency/developer/ccurrencylang/currencyformat.php).

#### Смотрите также

* [CCurrencyLang::CurrencyFormat](/api_help/currency/developer/ccurrencylang/currencyformat.php)

Новинки документации в соцсетях: