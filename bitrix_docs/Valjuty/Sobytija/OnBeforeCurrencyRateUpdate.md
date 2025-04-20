[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyRateUpdate (доступно с 14.0.0)

OnBeforeCurrencyRateUpdate
==========================

```
bool функция-обработчик(
	int ID,
	array arFields
);Копировать
```

OnBeforeCurrencyRateUpdate - событие, вызываемое перед обновлением существующего курса валюты. Позволяет изменить вносимые данные.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Код курса валюты. |
| arFields | Ассоциативный массив параметров курса валюты. Перечень допустимых ключей массива смотрите в [CCurrencyRates::Update](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__update.1f36666f.php). |

#### Возвращаемое значение

Может вернуть *false*, если нужно воспрепятствовать обновлению. В противном случае нужно вернуть значение *true*.

#### Смотрите также

* [CCurrencyRates::Update](/api_help/currency/developer/ccurrencyrates/ccurrencyrates__update.1f36666f.php)

Новинки документации в соцсетях: