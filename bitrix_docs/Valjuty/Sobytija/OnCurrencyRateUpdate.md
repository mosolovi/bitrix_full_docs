[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnCurrencyRateUpdate (доступно с 14.0.0)

OnCurrencyRateUpdate
====================

```
функция-обработчик(
	int ID,
	array arFields
);Копировать
```

OnCurrencyRateUpdate - событие, вызываемое в случае успешного изменения курса валюты.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Код курса валюты. |
| arFields | Ассоциативный массив параметров курса валюты. Перечень допустимых ключей массива смотрите в [CCurrencyRates::Update](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__update.1f36666f.php). |

#### Возвращаемое значение

Нет.

#### Смотрите также

* [CCurrencyRates::Update](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__update.1f36666f.php)

Новинки документации в соцсетях: