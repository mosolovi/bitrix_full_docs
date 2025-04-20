[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

GetCountryByID (доступен с 3.2.2, устарел с 14.10)

GetCountryByID
==============

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
array
CSaleLocation::GetCountryByID(
	int ID
);Копировать
```

Метод возвращает языконезависимые параметры страны с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код страны. |

#### Возвращаемые значения

Возвращается ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код страны. |
| NAME | Языконезависимое название страны. |
| SHORT\_NAME | Языконезависимое короткое название страны. |

Новинки документации в соцсетях: