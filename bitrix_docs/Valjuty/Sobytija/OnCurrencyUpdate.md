[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnCurrencyUpdate (доступно с 14.0.0)

OnCurrencyUpdate
================

```
функция-обработчик(
	string currency,
	array arFields
);Копировать
```

OnCurrencyUpdate - событие, вызываемое в случае успешного изменения валюты.

#### Параметры

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |
| arFields | Ассоциативный массив параметров валюты. Перечень допустимых ключей массива смотрите в [CCurrency::Update](/api_help/currency/developer/ccurrency/ccurrency__update.16586d51.php). |

#### Возвращаемое значение

Нет.

#### Смотрите также

* [CCurrency::Update](/api_help/currency/developer/ccurrency/ccurrency__update.16586d51.php)

Новинки документации в соцсетях: