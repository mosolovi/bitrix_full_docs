[Интернет-магазин](/api_help/sale/index.php)

[События](/api_help/sale/events/index.php)

События, связанные с изменением аффилиатов

События, связанные с изменением аффилиатов
==========================================

**Примечание:** перечисленные ниже события устарели с версии 15.5.0, но в продукте сохранена обратная совместимость. Поэтому их можно использовать, если в настройках модуля **Интернет-магазин** отмечена опция **Включить обработку устаревших событий**. Либо вы можете использовать [события нового ядра](http://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/index.php).

| Событие | Описание и параметры | Метод | С версии | До версии |
| --- | --- | --- | --- | --- |
| OnBeforeBAffiliateAdd | Вызывается до добавления аффилиата.   **Параметры**  |  |  | | --- | --- | | *$arFields* | Массив изменяемых параметров | | CSaleAffiliate::Add | 12.0.4 | 15.5.0 |
| OnAfterBAffiliateAdd | Вызывается после добавления аффилиата.   **Параметры**  |  |  | | --- | --- | | *$ID* | Код добавленного аффилиата. | | *arFields* | Массив параметров | | CSaleAffiliate::Add | 12.0.4 | 15.5.0 |
| OnBeforeAffiliateUpdate | Вызывается до обновления   **Параметры**  |  |  | | --- | --- | | *ID* | Код аффилиата | | *$arFields* | Массив изменяемых параметров | | CSaleAffiliate::Update | 12.0.4 | 15.5.0 |
| OnAfterAffiliateUpdate | Вызывается после обновления   **Параметры**  |  |  | | --- | --- | | *ID* | Код аффилиата | | *$arFields* | Массив параметров | | CSaleAffiliate::Update | 12.0.4 | 15.5.0 |
| OnBeforeAffiliateDelete | Вызывается перед удалением   **Параметры**  |  |  | | --- | --- | | *ID* | Код аффилиата | | CSaleAffiliate::Delete | 12.0.4 | 15.5.0 |
| OnAfterAffiliateDelete | Вызывается после удаления   **Параметры**  |  |  | | --- | --- | | *ID* | Код аффилиата | | *$bResult* | Результат удаления (true/false)Массив параметров | | CSaleAffiliate::Delete | 12.0.4 | 15.5.0 |
| OnBeforeAffiliateCalculate | Вызывается перед калькуляцией   **Параметры**  |  |  | | --- | --- | | *$arAffiliate* | Массив параметров аффилиата | | *$dateFrom*, *$dateTo* | Период калькуляции | | *$datePlanFrom*, *$datePlanTo* | Период определения плана | | CSaleAffiliate::CalculateAffiliate | 12.0.4 | 15.5.0 |
| OnAfterAffiliateCalculate | Вызывается после калькуляции   **Параметры**  |  |  | | --- | --- | | *affiliateID* | Код аффилиата | | CSaleAffiliate::CalculateAffiliate | 12.0.4 | 15.5.0 |
| OnBeforePayAffiliate | Вызывается перед выплатой суммы на счёт   **Параметры**  |  |  | | --- | --- | | *$arAffiliate* | Массив данных аффилиата. | | *$payType* | Статус что делать с суммой. | | CSaleAffiliate::PayAffiliate | 12.0.4 | 15.5.0 |
| OnAfterPayAffiliate | Вызывается после выплат   **Параметры**  |  |  | | --- | --- | | *affiliateID* | Код аффилиата | | CSaleAffiliate::PayAffiliate | 12.0.4 | 15.5.0 |
| OnBeforeAffiliatePlanAdd | Вызывается до сохранения плана   **Параметры**  |  |  | | --- | --- | | *$arFields* | Массив параметров плана | | CSaleAffiliatePlan::Add | 12.0.4 | 15.5.0 |
| OnAfterAffiliatePlanAdd | Вызывается после сохранения плана   **Параметры**  |  |  | | --- | --- | | *$ID* | Код плана | | *$arFields* | Массив параметров плана | | CSaleAffiliatePlan::Add | 12.0.4 | 15.5.0 |
| OnBeforeAffiliatePlanUpdate | Вызывается до обновления плана.   **Параметры**  |  |  | | --- | --- | | *$ID* | Код плана. | | *$arFields* | Массив параметров плана | | CSaleAffiliatePlan::Update | 12.0.4 | 15.5.0 |
| OnAfterAffiliatePlanUpdate | Вызывается после обновления плана.   **Параметры**  |  |  | | --- | --- | | *$ID* | Код плана. | | *$arFields* | Массив параметров плана | | CSaleAffiliatePlan::Update | 12.0.4 | 15.5.0 |
| OnBeforeAffiliatePlanDelete | Вызывается до удаления плана   **Параметры**  |  |  | | --- | --- | | *$ID* | Код плана | | CSaleAffiliatePlan::Delete | 12.0.4 | 15.5.0 |
| OnAfterAffiliatePlanDelete | Вызывается после удаления плана   **Параметры**  |  |  | | --- | --- | | *$ID* | Код плана | | *$bResult* | Результат удаления (true/false) | | CSaleAffiliatePlan::Delete | 12.0.4 | 15.5.0 |

Новинки документации в соцсетях: