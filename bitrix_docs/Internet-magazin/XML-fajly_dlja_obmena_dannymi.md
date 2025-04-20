[Интернет-магазин](/api_help/sale/index.php)

[XML-файлы для обмена данными](/api_help/sale/xml/index.php)

Описание файлов XML

Описание файлов XML
===================

Включить вкладки

Общее описание

Примеры файлов XML при обмене с 1С

### Общее описание

Данные для обмена хранятся в файлах:

* [import.xml](/api_help/sale/xml/import.php) — информация о разделах, товарах, группах
  маркировки



  В РФ в соответствии с Федеральным законом от 31 декабря 2017 г. № 487-ФЗ товары подлежат обязательной маркировке согласно утвержденному перечню.
    
    
  [Подробнее](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=42&LESSON_ID=12832)...
  товаров, размерах, типах цен, складах, свойствах товаров и единицах измерения;
* [offers.xml](/api_help/sale/xml/offers.php) — информация о предложениях товаров и их свойствах;
* [prices.xml](/api_help/sale/xml/prices.php) — информация о ценах предложений;
* [rests.xml](/api_help/sale/xml/rests.php) — информация об остатках предложений;
* [documents.xml](/api_help/sale/xml/documents.php) — информация о документах;
* [contragents.xml](/api_help/sale/xml/contragents.php) — информация о контрагентах;
* [references.xml](/api_help/sale/xml/references.php) — информация о пользовательских справочниках.

В конце названия каждого файла до точки перед расширением рекомендуем указывать случайное значение, чтобы файлы были уникальными. Это повышает безопасность при передаче данных.

При использовании пакетного обмена данных, когда информация выгружается порциями, важно, чтобы информация, на которую ссылается объект данных, была уже загружена на сайт. Например, в момент загрузки товаров на сайте уже должна быть информация о группах, свойствах, единицах измерений, а при загрузке предложений должна быть информация о товарах.

**Примечание.** Папку хранения картинок рекомендуем называть **import\_files**.

### Примеры файлов XML при обмене с 1С

[Модуль обмена с 1С](https://1c.1c-bitrix.ru/ecommerce/download.php) выгружает на сайт архив, структура которого описана ниже. Кликните по файлу и скачайте пример:

* [import.xml](https://dev.1c-bitrix.ru/upload/example-xml/import.xml) — корневой файл с информацией о группах/разделах, типах цен, складах и единицах измерения
* *goods* — папка с информацией о товарах. Если включены все опции выгрузки, в этой папке будут файлы:
  + [import.xml](https://dev.1c-bitrix.ru/upload/example-xml/goods/import.xml) — информация о товарах
  + [offers.xml](https://dev.1c-bitrix.ru/upload/example-xml/goods/offers.xml) — информация о торговых предложениях
  + [prices.xml](https://dev.1c-bitrix.ru/upload/example-xml/goods/prices.xml) — информация о ценах товаров и предложений
  + [rests.xml](https://dev.1c-bitrix.ru/upload/example-xml/goods/rests.xml) — информация об остатках товаров и предложений
* *properties* — папка с информацией о значении свойств для товаров и предложений, которые передаются в *goods*:
  + [import.xml](https://dev.1c-bitrix.ru/upload/example-xml/properties/import.xml) — информация о свойствах товаров
  + [offers.xml](https://dev.1c-bitrix.ru/upload/example-xml/properties/offers.xml) — информация о свойствах предложений
* [references.xml](https://dev.1c-bitrix.ru/upload/example-xml/properties/references.xml download) — информация о пользовательских справочниках, которые передаются на сайт в элементы highload-блоков

Новинки документации в соцсетях: