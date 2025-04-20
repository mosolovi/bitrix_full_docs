[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyRateAdd (доступно с 14.0.0)

OnBeforeCurrencyRateAdd
=======================

```
bool функция-обработчик(
	array arFields
);Копировать
```

OnBeforeCurrencyRateAdd - событие, вызываемое в методе [CCurrencyRates::Add](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__add.a9ea23d5.php) перед добавлением курса валюты и перед проверкой полей. Позволяет изменить вносимые данные либо вообще отменить запись.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров курса валюты. Перечень допустимых ключей массива смотрите в [CCurrencyRates::Add](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__add.a9ea23d5.php). |

#### Возвращаемое значение

Возвращает *false* при отказе, а *true* - при успешном разрешении на добавление.

#### Смотрите также

* [CCurrencyRates::Add](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__add.a9ea23d5.php)

Новинки документации в соцсетях: