[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnCurrencyRateAdd (доступно с 14.0.0)

OnCurrencyRateAdd
=================

```
функция-обработчик(
	int ID,
	array arFields
);Копировать
```

OnCurrencyRateAdd - событие, вызываемое в случае успешного добавления нового курса валюты.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Код курса валюты. |
| arFields | Ассоциативный массив параметров курса валюты. Перечень допустимых ключей массива смотрите в [CCurrencyRates::Add](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__add.a9ea23d5.php). |

#### Возвращаемое значение

Нет.

#### Смотрите также

* [CCurrencyRates::Add](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__add.a9ea23d5.php)

Новинки документации в соцсетях: