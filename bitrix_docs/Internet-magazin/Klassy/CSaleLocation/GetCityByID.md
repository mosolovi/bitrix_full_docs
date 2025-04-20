[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

GetCityByID (доступен с 3.2.2, устарел с 14.10)

GetCityByID
===========

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
array
CSaleLocation::GetCityByID(
	int ID
);Копировать
```

Метод возвращает языконезависимые параметры города с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код города. |

#### Возвращаемые значения

Возвращается ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код города. |
| NAME | Языконезависимое название города. |
| SHORT\_NAME | Языконезависимое короткое название города. |
| REGION\_ID | Код региона. |

Новинки документации в соцсетях: