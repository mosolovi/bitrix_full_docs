[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyUpdate (доступно с 14.0.0)

OnBeforeCurrencyUpdate
======================

```
bool функция-обработчик(
	string currency,
	array arFields
);Копировать
```

OnBeforeCurrencyUpdate - событие, вызываемое перед обновлением существующей валюты. Позволяет изменить вносимые данные.

#### Параметры

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |
| arFields | Ассоциативный массив параметров валюты. Перечень допустимых ключей массива смотрите в [CCurrency::Update](/api_help/currency/developer/ccurrency/ccurrency__update.16586d51.php). |

#### Возвращаемое значение

Может вернуть *false*, если нужно воспрепятствовать обновлению. В противном случае нужно вернуть значение *true*.

#### Смотрите также

* [CCurrency::Update](/api_help/currency/developer/ccurrency/ccurrency__update.16586d51.php)

Новинки документации в соцсетях: