[Валюты](/api_help/currency/index.php)

[События](/api_help/currency/events/index.php)

OnBeforeCurrencyAdd (доступно с 14.0.0)

OnBeforeCurrencyAdd
===================

```
bool функция-обработчик(
	array arFields
);Копировать
```

OnBeforeCurrencyAdd - событие, вызываемое в методе [CCurrency::Add](/api_help/currency/developer/ccurrency/ccurrency__add.17dc7357.php) перед добавлением валюты и перед проверкой полей. Позволяет изменить вносимые данные либо вообще отменить запись.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров валюты. Перечень допустимых ключей массива смотрите в [CCurrency::Add](/api_help/currency/developer/ccurrency/ccurrency__add.17dc7357.php). |

#### Возвращаемое значение

Возвращает *false* при отказе, возвращает *true* при успешном разрешении на добавление.

#### Смотрите также

* [CCurrency::Add](/api_help/currency/developer/ccurrency/ccurrency__add.17dc7357.php)

Новинки документации в соцсетях: