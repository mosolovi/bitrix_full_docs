[Интернет-магазин](/api_help/sale/index.php)

[События](/api_help/sale/events/index.php)

События, связанные с местоположениями

События, связанные с местоположениями
=====================================

**Примечание:** перечисленные ниже события устарели с версии 15.5.0, но в продукте сохранена обратная совместимость. Поэтому их можно использовать, если в настройках модуля **Интернет-магазин** отмечена опция **Включить обработку устаревших событий**. Либо вы можете использовать [события нового ядра](http://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/index.php).

  

| Событие | Описание и параметры | Метод | С версии | До версии |
| --- | --- | --- | --- | --- |
| OnCityAdd | Вызывается после добавления города.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор города | | *arFields* | Массив полей города | | [AddCity](/api_help/sale/classes/csalelocation/csalelocation__addcity.d2d048d2.php) | 4.0.6 | 15.5.0 |
| OnCityDelete | Вызывается после удаления города.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор города | | [DeleteCity](/api_help/sale/classes/csalelocation/csalelocation__deletecity.339c5a43.php) | 4.0.6 | 15.5.0 |
| OnCityUpdate | Вызывается после изменения города.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор города | | *arFields* | Массив полей полей города | | [UpdateCity](/api_help/sale/classes/csalelocation/csalelocation__updatecity.3fe4165d.php) | 4.0.6 | 15.5.0 |
| OnBeforeCityAdd | Вызывается перед добавлением города   **Параметры**  |  |  | | --- | --- | | *arFields* | Массив новых параметров. | | [AddCity](/api_help/sale/classes/csalelocation/csalelocation__addcity.d2d048d2.php) | 4.0.6 | 15.5.0 |
| OnBeforeCityDelete | Вызывается перед удалением города.   **Параметры**  |  |  | | --- | --- | | *ID* | Код записи города | | [DeleteCity](/api_help/sale/classes/csalelocation/csalelocation__deletecity.339c5a43.php) | 4.0.6 | 15.5.0 |
| OnBeforeCityUpdate | Вызывается перед обновлением города   **Параметры**  |  |  | | --- | --- | | *ID* | Код записи города. | | *arFields* | Массив новых параметров города. | | [UpdateCity](/api_help/sale/classes/csalelocation/csalelocation__updatecity.3fe4165d.php) | 4.0.6 | 15.5.0 |
| OnRegionDelete | Вызывается после удаления региона.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор региона | | CSaleLocation::DeleteRegion | 12.0.0 | 15.5.0 |
| OnBeforeRegionDelete | Вызывается до удаления региона, может быть использовано для отмены удаления.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор региона | | CSaleLocation::DeleteRegion | 12.0.0 | 15.5.0 |
| OnRegionUpdate | Вызывается после обновления региона.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор региона | | *arFields* | Массив полей региона | | CSaleLocation::UpdateRegion | 12.0.0 | 15.5.0 |
| OnBeforeRegionUpdate | Вызывается до обновления региона, может быть использовано для отмены или модификации данных   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор региона | | *arFields* | Массив полей региона | | CSaleLocation::UpdateRegion | 12.0.0 | 15.5.0 |
| OnBeforeRegionAdd | Вызывается перед добавлением региона.   **Параметры**  |  |  | | --- | --- | | *arFields* | Массив полей региона. | | CSaleLocation::AddRegion | 12.0.0 | 15.5.0 |
| OnRegionAdd | Вызывается после добавлением региона   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор региона | | *arFields* | Массив полей региона | | CSaleLocation::AddRegion | 12.0.0 | 15.5.0 |
| OnCountryAdd | Вызывается после добавления страны   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор страны | | *arFields* | Массив полей страны | | [AddCountry](/api_help/sale/classes/csalelocation/csalelocation__addcountry.cbe82f7a.php) | 4.0.6 | 15.5.0 |
| OnCountryDelete | Вызывается после удаления страны.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор страны | | [DeleteCountry](/api_help/sale/classes/csalelocation/csalelocation__deletecountry.e37a14ed.php) | 4.0.6 | 15.5.0 |
| OnCountryUpdate | Вызывается после изменения страны   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор страны | | *arFields* | Массив полей страны | | [UpdateCountry](/api_help/sale/classes/csalelocation/csalelocation__updatecountry.d8fa5b90.php) | 4.0.6 | 15.5.0 |
| OnBeforeCountryAdd | Вызывается перед добавлением страны.   **Параметры**  |  |  | | --- | --- | | *arFields* | Массив новых параметров страны | | [AddCountry](/api_help/sale/classes/csalelocation/csalelocation__addcountry.cbe82f7a.php) | 4.0.6 | 15.5.0 |
| OnBeforeCountryDelete | Вызывается перед удалением страны.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор страны | | [DeleteCountry](/api_help/sale/classes/csalelocation/csalelocation__deletecountry.e37a14ed.php) | 4.0.6 | 15.5.0 |
| OnBeforeCountryUpdate | Вызывается перед обновлением страны.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор страны | | *arFields* | Массив новых параметров страны | | [UpdateCountry](/api_help/sale/classes/csalelocation/csalelocation__updatecountry.d8fa5b90.php) | 4.0.6 | 15.5.0 |
| OnLocationDelete | Вызывается после удаления местоположения   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор местоположения | | [Delete](/api_help/sale/classes/csalelocation/csalelocation__delete.008e0aa2.php) | 4.0.6 | 15.5.0 |
| OnLocationDeleteAll | Вызывается после удаления всех местоположений.   Параметров нет | [DeleteAll](/api_help/sale/classes/csalelocation/csalelocation__deleteall.1cda6559.php) | 4.0.6 | 15.5.0 |
| OnLocationAdd | Вызывается после добавления местоположения   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор местоположения | | *arFields* | Массив полей местоположения | | [AddLocation](/api_help/sale/classes/csalelocation/csalelocation__addlocation.21fe0465.php) | 4.0.6 | 15.5.0 |
| OnLocationUpdate | Вызывается после обновления местоположения.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор местоположения | | *arFields* | Массив полей местоположения | | [UpdateLocation](/api_help/sale/classes/csalelocation/csalelocation__updatelocation.3c5a6205.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationAdd | Вызывается перед добавлением местоположения   **Параметры**  |  |  | | --- | --- | | *arFields* | Массив новых параметров местоположения | | [AddLocation](/api_help/sale/classes/csalelocation/csalelocation__addlocation.21fe0465.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationDelete | Вызывается перед удалением местоположения.   **Параметры**  |  |  | | --- | --- | | *ID* | Код записи местоположения | | [Delete](/api_help/sale/classes/csalelocation/csalelocation__delete.008e0aa2.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationDeleteAll | Вызывается перед удалением всех местоположений.   Параметров нет. | [DeleteAll](/api_help/sale/classes/csalelocation/csalelocation__deleteall.1cda6559.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationUpdate | Вызывается перед изменением местоположения.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор местоположения | | *arFields* | Массив полей местоположения | | [UpdateLocation](/api_help/sale/classes/csalelocation/csalelocation__updatelocation.3c5a6205.php) | 4.0.6 | 15.5.0 |
| OnLocationGroupAdd | Вызывается после добавления группы местоположений   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор группы местоположений | | *arFields* | Массив полей группы местоположений | | [Add](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__add.3520254b.php) | 4.0.6 | 15.5.0 |
| OnLocationGroupDelete | Вызывается после удаления группы местоположений.   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор группы местоположений | | [Delete](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__delete.d96420be.php) | 4.0.6 | 15.5.0 |
| OnLocationGroupUpdate | Вызывается после после группы местоположений   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор группы местоположений | | *arFields* | Массив полей группы местоположений | | [Update](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__update.c02c467b.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationGroupAdd | Вызывается перед добавлением группы местоположений.   **Параметры**  |  |  | | --- | --- | | *arFields* | Массив новых параметров группы местоположений | | [Add](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__add.3520254b.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationGroupDelete | Вызывается перед удалением группы местоположений.   **Параметры**  |  |  | | --- | --- | | *ID* | Код записи группы местоположений | | [Delete](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__delete.d96420be.php) | 4.0.6 | 15.5.0 |
| OnBeforeLocationGroupUpdate | Вызывается перед изменением группы местоположений   **Параметры**  |  |  | | --- | --- | | *ID* | Идентификатор группы местоположений | | *arFields* | Массив полей группы местоположений | | [Update](/api_help/sale/classes/csalelocationgroup/csalelocationgroup__update.c02c467b.php) | 4.0.6 | 15.5.0 |

Новинки документации в соцсетях: