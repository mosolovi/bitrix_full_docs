[Интернет-магазин](/api_help/sale/index.php)

Интернет-магазин в ядре D7

Интернет-магазин в ядре D7
==========================

Включить вкладки

Список классов

События

Приёмы работы с методами интернет-магазина

Дополнительно

### Список классов

Список классов модуля **Интернет-магазин** в ядре D7:

| Класс, пространство имен | Описание |
| --- | --- |
| [Archive](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/archive/index.php) | Класс для работы с архивацией заказов. |
| [Basket](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/basket/index.php) | Класс для работы с корзиной. Наследник класса `\Bitrix\Sale\BasketItemCollection`. |
| [BasketBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/basketbase/index.php) | Класс для работы с корзиной. |
| [BasketItemCollection](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/basketitemcollection/index.php) | Класс коллекции товарных позиций. |
| [BusinessValue](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/businessvalue/index.php) | Класс для работы с бизнес-смыслами. |
| [Configuration](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/configuration/index.php) | Класс для работы с настройками резервирования товаров, складского учета и настройками смены статусов интернет-магазина. |
| [Delivery](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/delivery/index.php) | Пространство имен, содержащее классы для работы со службами доставок. |
| [Discount](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/discount/index.php) | Пространство имен, содержащее подпространства, классы и методы для расчета всех скидок (каталога и магазина) и округления цен для корзины или заказа. |
| [DiscountCouponsManager](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/discountcouponsmanager/index.php) | Класс для работы с купонами при расчетах. |
| [Fuser](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/fuser/index.php) | Класс для получения идентификатора покупателя. |
| [Internals](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/internals/index.php) | Подпространство, содержащее классы для работы с таблицами модуля **Интернет-магазин**. |
| [Location](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/location/index.php) | Подпространство имен, содержащее классы для работы с местоположениями. |
| [Notify](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/notify/index.php) | Класс для работы с уведомлениями. |
| [Order](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/order/index.php) | Класс для работы с заказами. |
| [OrderBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/orderbase/index.php) | Базовый класс для работы с заказами. |
| [OrderDiscountManager](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/orderdiscountmanager/index.php) | Класс для работы с правилами корзины при расчетах. |
| [Payment](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/payment/index.php) | Класс оплаты. |
| [PaymentCollection](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/paymentcollection/index.php) | Класс коллекции оплат. |
| [PropertyValueCollectionBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/propertyvaluecollectionbase/index.php) | Базовый класс коллекции свойств заказа. |
| [ProviderBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/providerbase/index.php) | Базовый класс для работы с провайдерами магазина. |
| [Result](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/result/index.php) | Класс для работы с результатами. |
| [SalesZone](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/saleszone/index.php) | Класс для задания зоны обслуживания магазином. |
| [Services](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/services/index.php) | Базовая общая часть служб доставок и платежных систем. |
| [Shipment](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/shipment/index.php) | Класс отгрузок. |
| [ShipmentCollection](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/shipmentcollection/index.php) | Класс коллекции отгрузок. |
| [ShipmentItem](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/shipmentitem/index.php) | Класс элемента отгрузки. |
| [ShipmentItemStore](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/shipmentitemstore/index.php) | Класс штрих-кодов элементов отгрузки. |
| [StatusBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/statusbase/index.php) | Базовый класс статусов. |
| [Tax](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/tax/index.php) | Класс налогов. |
| [TradingPlatform](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/tradingplatform/index.php) | Класс для работы с торговыми платформами. |

### События

Список событий модуля **Интернет-магазин** в ядре D7:

* [События компонента оформления заказа](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/event_sale_order_ajax.php)
* [События на изменение значения поля](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/sale_setfields.php)
* [События на завершение пересчета](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/order_final_action.php)
* [События на сохранение заказа](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/order_saved.php)
* [События после сохранения сущности](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/sale_entitysaved.php)
* [Сохранение заказа: особые события](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/order_special.php)
* [События сохранения корзины](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/basket_saved.php)
* [События обновления корзины](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/basket_updated.php)
* [События отгрузки](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/shipment.php)
* [События платежных систем](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/payment_events.php)
* [События при непосредственном удалении сущностей из базы](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/sale_deleted.php)
* [События работы с кассами и чеками](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/cash_desk_and_checks.php)
* [События служб доставок](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/events/delivery_events.php)

### Приёмы работы с методами интернет-магазина

Примеры работы с методами следующих сущностей модуля **Интернет-магазин** в ядре D7:

* [Заказы](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/orders.php)
* [Свойства заказа](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/order_property.php)
* [Значения свойств заказа](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/property.php)
* [Корзина](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/basket.php)
* [Свойства корзины](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/basket_properties.php)
* [Оплаты](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/payments.php)
* [Отгрузки](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/shipment.php)
* [Состав отгрузки](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/technique/shipment_item_collection.php)

### Дополнительно

* [Работа через реестр](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/registry_work.php).

Новинки документации в соцсетях: