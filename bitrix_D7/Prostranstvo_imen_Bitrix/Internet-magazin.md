[Пространство имён Bitrix](/api_d7/bitrix/index.php)

Интернет-магазин

Интернет-магазин
================

`\Bitrix\Sale` – пространство имен модуля **Интернет-магазин**.

Перед использованием модуля необходимо проверить установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule(
	'sale'
);Копировать
```

| Класс, пространство имен | Описание |
| --- | --- |
| [Archive](/api_d7/bitrix/sale/classes/archive/index.php) | Класс для работы с архивацией заказов. |
| [Basket](/api_d7/bitrix/sale/classes/basket/index.php) | Класс для работы с корзиной. Наследник класса `\Bitrix\Sale\BasketItemCollection`. |
| [BasketBase](/api_d7/bitrix/sale/classes/basketbase/index.php) | Класс для работы с корзиной. |
| [BasketItemCollection](/api_d7/bitrix/sale/classes/basketitemcollection/index.php) | Класс коллекции товарных позиций. |
| [BusinessValue](/api_d7/bitrix/sale/classes/businessvalue/index.php) | Класс для работы с бизнес-смыслами. |
| [Configuration](/api_d7/bitrix/sale/classes/configuration/index.php) | Класс для работы с настройками резервирования товаров, складского учета и настройками смены статусов интернет-магазина. |
| [Delivery](/api_d7/bitrix/sale/classes/delivery/index.php) | Пространство имен, содержащее классы для работы со службами доставок. |
| [Discount](/api_d7/bitrix/sale/classes/discount/index.php) | Пространство имен, содержащее подпространства, классы и методы для расчета всех скидок (каталога и магазина) и округления цен для корзины или заказа. |
| [DiscountCouponsManager](/api_d7/bitrix/sale/classes/discountcouponsmanager/index.php) | Класс для работы с купонами при расчетах. |
| [Fuser](/api_d7/bitrix/sale/classes/fuser/index.php) | Класс для получения идентификатора покупателя. |
| [Internals](/api_d7/bitrix/sale/classes/internals/index.php) | Подпространство, содержащее классы для работы с таблицами модуля **Интернет-магазин**. |
| [Location](/api_d7/bitrix/sale/classes/location/index.php) | Подпространство имен, содержащее классы для работы с местоположениями. |
| [Notify](/api_d7/bitrix/sale/classes/notify/index.php) | Класс для работы с уведомлениями. |
| [Order](/api_d7/bitrix/sale/classes/order/index.php) | Класс для работы с заказами. |
| [OrderBase](/api_d7/bitrix/sale/classes/orderbase/index.php) | Базовый класс для работы с заказами. |
| [OrderDiscountManager](/api_d7/bitrix/sale/classes/orderdiscountmanager/index.php) | Класс для работы с правилами корзины при расчетах. |
| [Payment](/api_d7/bitrix/sale/classes/payment/index.php) | Класс оплаты. |
| [PaymentCollection](/api_d7/bitrix/sale/classes/paymentcollection/index.php) | Класс коллекции оплат. |
| [PropertyValueCollectionBase](/api_d7/bitrix/sale/classes/propertyvaluecollectionbase/index.php) | Базовый класс коллекции свойств заказа. |
| [ProviderBase](/api_d7/bitrix/sale/classes/providerbase/index.php) | Базовый класс для работы с провайдерами магазина. |
| [Result](/api_d7/bitrix/sale/classes/result/index.php) | Класс для работы с результатами. |
| [SalesZone](/api_d7/bitrix/sale/classes/saleszone/index.php) | Класс для задания зоны обслуживания магазином. |
| [Services](/api_d7/bitrix/sale/classes/services/index.php) | Базовая общая часть служб доставок и платежных систем. |
| [Shipment](/api_d7/bitrix/sale/classes/shipment/index.php) | Класс отгрузок. |
| [ShipmentCollection](/api_d7/bitrix/sale/classes/shipmentcollection/index.php) | Класс коллекции отгрузок. |
| [ShipmentItem](/api_d7/bitrix/sale/classes/shipmentitem/index.php) | Класс элемента отгрузки. |
| [ShipmentItemStore](/api_d7/bitrix/sale/classes/shipmentitemstore/index.php) | Класс штрих-кодов элементов отгрузки. |
| [StatusBase](/api_d7/bitrix/sale/classes/statusbase/index.php) | Базовый класс статусов. |
| [Tax](/api_d7/bitrix/sale/classes/tax/index.php) | Класс налогов. |
| [TradingPlatform](/api_d7/bitrix/sale/classes/tradingplatform/index.php) | Класс для работы с торговыми платформами. |

Новинки документации в соцсетях: