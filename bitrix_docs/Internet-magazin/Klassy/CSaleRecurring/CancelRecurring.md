[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleRecurring](/api_help/sale/classes/csalerecurring/index.php)

CancelRecurring (доступен с 4.0.6)

CancelRecurring
===============

```
bool
CSaleRecurring::CancelRecurring(
	int ID
	string val[,
	string description = ""]
);Копировать
```

Метод осуществляет отмену продления подписки с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код записи с информацией о продлении. |
| val | "Y", если подписка отменяется, и "N", если подписка восстанавливается. |
| description | Причина отмены подписки. |

#### Возвращаемые значения

Метод возвращает код отменяемой записи или *false* в случае ошибки.

Новинки документации в соцсетях: