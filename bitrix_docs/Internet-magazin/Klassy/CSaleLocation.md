[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleLocation](/api_help/sale/classes/csalelocation/index.php)

Класс CSaleLocation (доступен с 3.2.2, устарел с 14.10)

Класс CSaleLocation
===================

Класс устарел. Рекомендуется использовать методы класса [Bitrix\Sale\Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php).

#### Методы класса

| Метод | Описание | С версии | Устарел с версии |
| --- | --- | --- | --- |
| [GetCountryByID](/api_help/sale/classes/csalelocation/csalelocation__getcountrybyid.bc803b85.php) | Метод возвращает языконезависимые параметры страны с кодом ID. | 3.2.2 | 14.10 |
| [GetCountryLangByID](/api_help/sale/classes/csalelocation/csalelocation__getcountrylangbyid.aef8761b.php) | Метод возвращает языкозависимые параметры страны по ее коду ID и языку strLang. | 3.2.2 | 14.10 |
| [GetCityByID](/api_help/sale/classes/csalelocation/csalelocation__getcitybyid.fb724f2b.php) | Метод возвращает языконезависимые параметры города с кодом ID. | 3.2.2 | 14.10 |
| [GetCityLangByID](/api_help/sale/classes/csalelocation/csalelocation__getcitylangbyid.f2bc091a.php) | Метод возвращает языкозависимые параметры города по его коду ID и языку strLang. | 3.2.2 | 14.10 |
| [UpdateCountry](/api_help/sale/classes/csalelocation/csalelocation__updatecountry.d8fa5b90.php) | Метод изменяет параметры страны с кодом ID на новые параметры из массива arFields. | 3.2.2 | 14.10 |
| [DeleteCountry](/api_help/sale/classes/csalelocation/csalelocation__deletecountry.e37a14ed.php) | Метод удаляет страну с кодом ID. Связаные с этой страной местоположения не изменяются. | 3.2.2 | 14.10 |
| [UpdateCity](/api_help/sale/classes/csalelocation/csalelocation__updatecity.3fe4165d.php) | Метод изменяет параметры города с кодом ID на значения из массива arFields. | 3.2.2 | 14.10 |
| [DeleteCity](/api_help/sale/classes/csalelocation/csalelocation__deletecity.339c5a43.php) | Метод удаляет город с кодом ID. Местоположение, с которым связан этот город, не изменяется. | 3.2.2 | 14.10 |
| [UpdateLocation](/api_help/sale/classes/csalelocation/csalelocation__updatelocation.3c5a6205.php) | Метод обновляет параметры местоположения с кодом ID в соответствии с параметрами из массива arFields. | 3.2.2 | 14.10 |
| [Add](/api_help/sale/classes/csalelocation/csalelocation__add.92483b06.php) | Метод добавляет новое местоположение включая страну и город местоположения, если нужно. | 3.2.2 | 14.10 |
| [Update](/api_help/sale/classes/csalelocation/csalelocation__update.a6601f1c.php) | Метод обновляет параметры местоположения с кодом ID в соответствии с параметрами из массива arFields. Обновляются также страна и город этого местоположения. | 3.2.2 | 14.10 |
| [Delete](/api_help/sale/classes/csalelocation/csalelocation__delete.008e0aa2.php) | Метод удаляет местоположение с кодом ID. Метод также удаляет город этого местоположения, страну этого местоположения (если она не входит больше ни в одно другое местоположение), а так же связи этого местоположения с группами местоположений и службами доставки. | 3.2.2 | 14.10 |
| [GetList](/api_help/sale/classes/csalelocation/csalelocation__getlist.a60c2ce1.php) | Метод возвращает набор местоположений, удовлетворяющих фильтру arFilter. | 3.3.0 | 14.10 |
| [GetByID](/api_help/sale/classes/csalelocation/csalelocation__getbyid.bbc61011.php) | Метод возвращает параметры местоположения с кодом ID, включая параметры страны и города. | 3.3.0 | 14.10 |
| [GetCountryList](/api_help/sale/classes/csalelocation/csalelocation__getcountrylist.c37e68f6.php) | Метод возвращает набор стран по фильтру arFilter, отсортированный по массиву arOrder. | 3.3.0 | 14.10 |
| [AddCountry](/api_help/sale/classes/csalelocation/csalelocation__addcountry.cbe82f7a.php) | Метод добавляет новую страну с параметрами из массива arFields. | 3.3.0 | 14.10 |
| [AddCity](/api_help/sale/classes/csalelocation/csalelocation__addcity.d2d048d2.php) | Метод добавляет новый город с параметрами из массива arFields. | 3.3.0 | 14.10 |
| [AddLocation](/api_help/sale/classes/csalelocation/csalelocation__addlocation.21fe0465.php) | Метод добавляет новое местоположение на основании параметров массива arFields. | 3.3.0 | 14.10 |
| [DeleteAll](/api_help/sale/classes/csalelocation/csalelocation__deleteall.1cda6559.php) | Метод удаляет все местоположения из базы. | 3.3.5 | 14.10 |
| `GetByZIP($zipCode)` | Метод возвращает местоположение по почтовому индексу. | 3.3.5 | 14.10 |
| `GetLocationZIP($location)` | Метод возвращает почтовый индекс по местоположению. | 3.3.5 | 14.10 |

Новинки документации в соцсетях: