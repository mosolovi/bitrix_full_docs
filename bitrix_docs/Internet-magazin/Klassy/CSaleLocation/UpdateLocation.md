[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

UpdateLocation (доступен с 3.2.2, устарел с 14.10)

UpdateLocation
==============

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

```
int
CSaleLocation::UpdateLocation(
	int ID,
	array arFields
);Копировать
```

Метод обновляет параметры местоположения с кодом ID в соответствии с параметрами из массива arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код местоположения. |
| arFields | Ассоциативный массив параметров местоположения с ключами:  * **SORT** - индекс сортировки; * **COUNTRY\_ID** - код страны; * **REGION\_ID** - код региона; * **CITY\_ID** - код города (если такой город уже есть, иначе код должен быть нулем, и должен быть заполнен ключ CITY). |

#### Возвращаемые значения

Возвращается код измененного местоположения или *false* в случае ошибки.

Новинки документации в соцсетях: