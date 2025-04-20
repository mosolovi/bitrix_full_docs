[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleDiscount](/api_help/sale/classes/csalediscount/index.php)

GetByID (доступен с 3.3.1)

GetByID
=======

С версии 15.5 класс считается устаревшим и строго не рекомендованным к использованию. Вместо него используйте методы класса [\Bitrix\Sale\Discount](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/discount/index.php).

```
array
CSaleDiscount::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры скидки с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код скидки. |

#### Возвращаемые значения

Ассоциативный массив параметров скидки с ключами. Описание ключей смотрите [здесь](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/internals/discounttable/index.php#fields)

Новинки документации в соцсетях: