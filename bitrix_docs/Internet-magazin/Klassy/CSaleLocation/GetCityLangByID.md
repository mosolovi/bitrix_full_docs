[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

GetCityLangByID (доступен с 3.2.2, устарел с 14.10)

GetCityLangByID
===============

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
array
CSaleLocation::GetCityLangByID(
	int ID,
	string strLang = LANGUAGE_ID
);Копировать
```

Метод возвращает языкозависимые параметры города по его коду ID и языку strLang. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код города. |
| strLang | Язык. По умолчанию равен текущему языку. |

#### Возвращаемые значения

Возвращается ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код записи. |
| CITY\_ID | Код города. |
| LID | Язык. |
| NAME | Языкозависимое название города. |
| SHORT\_NAME | Языкозависимое короткое название города. |

Новинки документации в соцсетях: