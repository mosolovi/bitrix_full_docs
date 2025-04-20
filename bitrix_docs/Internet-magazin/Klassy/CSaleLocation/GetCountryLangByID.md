[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

GetCountryLangByID (доступен с 3.2.2, устарел с 14.10)

GetCountryLangByID
==================

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
array
CSaleLocation::GetCountryLangByID(
	int ID,
	string strLang = LANGUAGE_ID
);Копировать
```

Метод возвращает языкозависимые параметры страны по ее коду ID и языку strLang. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код страны. |
| strLang | Язык. По умолчанию берется текущий язык. |

#### Возвращаемые значения

Возвращается ассоциативный массив с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код записи. |
| COUNTRY\_ID | Код страны. |
| LID | Язык. |
| NAME | Языкозависимое название страны. |
| SHORT\_NAME | Языкозависимое короткое название страны. |

Новинки документации в соцсетях: