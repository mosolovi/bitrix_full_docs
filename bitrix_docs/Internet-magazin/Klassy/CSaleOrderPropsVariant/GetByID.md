[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderPropsVariant](/api_help/sale/classes/csaleorderpropsvariant/index.php)

GetByID (доступен с 3.3.0)

GetByID
=======

```
array
CSaleOrderPropsVariant::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры варианта с кодом ID значения свойства заказа. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код варианта значения свойства заказа. |

#### Возвращаемые значения

Возвращается ассоциативный массив значений параметров заказа с ключами:

| Код | Описание |
| --- | --- |
| ID | Код варианта значения свойства заказа. |
| ORDER\_PROPS\_ID | Код свойства заказа. |
| NAME | Название варианта. |
| VALUE | Значение варианта. |
| SORT | Индекс сортировки. |
| DESCRIPTION | Описание варианта значения свойства заказа. |

Новинки документации в соцсетях: