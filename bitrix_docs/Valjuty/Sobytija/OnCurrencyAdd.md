[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnCurrencyAdd (доступно с 14.0.0)

OnCurrencyAdd
=============

```
функция-обработчик(
	string currency,
	array arFields
);Копировать
```

OnCurrencyAdd - событие, вызываемое в случае успешного добавления новой валюты.

#### Параметры

| Параметр | Описание |
| --- | --- |
| currency | Код валюты. |
| arFields | Ассоциативный массив параметров валюты. Перечень допустимых ключей массива смотрите в [CCurrency::Add](/api_help/currency/developer/ccurrency/ccurrency__add.17dc7357.php). |

#### Возвращаемое значение

Нет.

#### Смотрите также

* [CCurrency::Add](/api_help/currency/developer/ccurrency/ccurrency__add.17dc7357.php)

Новинки документации в соцсетях: