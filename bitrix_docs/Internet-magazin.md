[Интернет-магазин](/api_help/sale/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Компоненты 2.0

### Описание

Информация представленная в данном разделе содержит сведения о классах и функциях модуля **Интернет-Магазин**, необходимых для организации продажи товаров и услуг через Интернет, создания интернет-магазинов и эффективного управления электронными каналами продаж товаров и услуг.

Перед использованием модуля необходимо проверить, установлен ли он и подключить его при помощи конструкции:

```
<?
if (CModule::IncludeModule("sale"))
{
	//здесь можно использовать функции модуля
}
?>Копировать
```

#### Некоторые термины модуля

**Базовая валюта для данного сайта** - валюта, в которой осуществляются операции по продаже товаров на данном сайте. Устанавливается на странице глобальных настроек модуля **Интернет-Магазин**. Понятие базовой валюты в модуле **Интернет-Магазин** отличается от понятия базовой валюты в модуле **Валюты**.

### Компоненты 2.0

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| **Аффилиаты** | | |
| [Отчет аффилиата](https://dev.1c-bitrix.ru/user_help/components/magazin/affiliates/sale_affiliate_account.php) | **sale.affiliate.account** | Отображает движение денег на счете аффилиата. |
| [Технические инструкции аффилиата](https://dev.1c-bitrix.ru/user_help/components/magazin/affiliates/sale_affiliate_instructions.php) | **sale.affiliate.instructions** | Служит для для вывода технических инструкций для аффилиата. |
| [Аффилиатские планы](https://dev.1c-bitrix.ru/user_help/components/magazin/affiliates/sale_affiliate_plans.php) | **sale.affiliate.plans** | Выводит список всех аффилиатских планов, определённых в системе. |
| [Регистрация аффилиата](https://dev.1c-bitrix.ru/user_help/components/magazin/affiliates/sale_affiliate_register.php) | **sale.affiliate.register** | Служит для создания страницы регистрации аффилиата. |
| [Отчет по программе аффилиата](https://dev.1c-bitrix.ru/user_help/components/magazin/affiliates/sale_affiliate_report.php) | **sale.affiliate.report** | Отображает список проданных товаров от авторизованного аффилиата за установленный период времени. |
| **Корзина** | | |
| [Корзина](https://dev.1c-bitrix.ru/user_help/components/magazin/basket/sale_basket_basket.php) | **sale.basket.basket** | Отображает список товаров, отправленных пользователем в корзину. |
| [Ссылка на корзину](https://dev.1c-bitrix.ru/user_help/components/magazin/basket/sale_basket_basket_line.php) | **sale.basket.basket.line** | В зависимости от настроек отображает ссылки на корзину пользователя и на его персональный раздел либо только на корзину. |
| [Малая корзина для почты](https://dev.1c-bitrix.ru/user_help/components/magazin/basket/sale_basket_basket_small_mail.php) | **sale.basket.basket.small.mail** | Отображает для почты список товаров, находящихся в корзине пользователя. |
| **Персональный раздел** | | |
| [Вывод полей заказа](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_business_value_mail.php) | **sale.business.value.mail** | Выводит список полей заказа по коду заказа. |
| [Персональный раздел пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_section.php) | **sale.personal.section** | Организует персональный раздел пользователя. |
| [Добавление средств на счет текущего пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_account_pay.php) | **sale.account.pay** | Позволяет добавить средства на внутренний счет текущего пользователя. |
| [Счета текущего пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_account.php) | **sale.personal.account** | Отображает состояние внутреннего счета текущего пользователя в доступной валюте. |
| [Пластиковые карты пользователя (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_cc.php) | **sale.personal.cc** | Используется для управления пластиковыми картами текущего пользователя. |
| [Редактирование пластиковых карт](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_cc_detail.php) | **sale.personal.cc.detail** | Служит для редактирования пластиковых карт пользователя. |
| [Список пластиковых карт текущего пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_cc_list.php) | **sale.personal.cc.list** | Выводит список пластиковых карт текущего пользователя. |
| [Заказы пользователя (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_order.php) | **sale.personal.order** | Отображает список заказов текущего пользователя с ссылками для перехода к просмотру детальной информации, отмене заказа, к оформлению повторного заказа. Можно управлять адресами переходов по этим страницам с помощью настроек ЧПУ. |
| [Отмена заказа](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_order_cancel.php) | **sale.personal.order.cancel** | Позволяет отменить заказ. |
| [Подробная информация о заказе](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_order_detail.php) | **sale.personal.order.detail** | Выводит подробную информацию по заказу. |
| [Подробная информация о заказе для почты](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_order_detail_mail.php) | **sale.personal.order.detail.mail** | Выводит подробную информацию по заказу для почты. |
| [Список заказов](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_order_list.php) | **sale.personal.order.list** | Выводит фильтр и список заказов пользователя. |
| [Профили пользователя (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_profile.php) | **sale.personal.profile** | Служит для управления профилями текущего пользователя. |
| [Редактирование профиля](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_profile_detail.php) | **sale.personal.profile.detail** | Позволяет редактировать профиль пользователя. |
| [Список профилей текущего пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_profile_list.php) | **sale.personal.profile.list** | Выводит список профилей текущего пользователя. |
| [Подписки пользователя (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_subscribe.php) | **sale.personal.subscribe** | Используется для управления подписками текущего пользователя. |
| [Отмена подписки](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_subscribe_cancel.php) | **sale.personal.subscribe.cancel** | Позволяет отменить подписку. |
| [Список подписок текущего пользователя](https://dev.1c-bitrix.ru/user_help/components/magazin/profiles/sale_personal_subscribe_list.php) | **sale.personal.subscribe.list** | Выводит список подписок текущего пользователя. |
| **Процедура оформления заказа** | | |
| [Калькулятор доставки (AJAX)](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_ajax_delivery_calculator.php) | **sale.ajax.delivery.calculator** | Выводит динамический калькулятор доставки. |
| [Одношаговое оформление заказа](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_order_ajax.php) | **sale.order.ajax** | Служит для оформления заказа на одной странице с использованием технологии AJAX. |


| [Подключение платежной системы](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_order_payment.php) | **sale.order.payment** | Осуществляет подключение платежной системы. |
| [Смена способа оплаты](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_order_payment_change.php) | **sale.order.payment.change** | Осуществляет смену платежной системы для оплаты заказа. |
| [Подключение обработчика результата платежной системы](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_order_payment_receive.php) | **sale.order.payment.receive** | Осуществляет подключение скрипта для получения результата от платежной системы. |
| [Привязка к местоположению: выпадающие списки](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_location_selector_steps.php) | **sale.location.selector.steps** | Выводит форму, в которой выбор местоположения осуществляется с помощью последовательного выбора вариантов из выпадающего списка. |
| [Привязка к местоположению: строка поиска](https://dev.1c-bitrix.ru/user_help/components/magazin/zakaz/sale_location_selector_search.php) | **sale.location.selector.search** | Выводит форму, в которой выбор местоположения осуществляется с помощью ввода запроса в строку поиска. |
| **Экспорт заказов** | | |
| [Экспорт заказов в "1С:Предприятие"](https://dev.1c-bitrix.ru/user_help/components/magazin/export_zakaz/sale_export_1c.php) | **sale.export.1c** | Служит для экспорта заказов в "1С:Предприятие" в формате CommerceML v2. |
| **Информация о товарах** | | |
| [Выбор товара для получения подарка](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_gift_main_products.php) | **sale.gift.main.products** | Служит для отображения блока товаров, которые нужно купить для получения предложенного подарка. |
| [Подарки к товарам в корзине](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_gift_basket.php) | **sale.gift.basket** | Служит для отображения товаров, которые будут предложены в качестве подарков к текущей корзине покупателя. |
| [Подарки к товарам конкретного раздела](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_products_gift_section.php) | **sale.products.gift.section** | Служит отображения подарков к товарам заданного раздела. |
| [Подарки к выбранному товару](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_products_gift.php) | **sale.products.gift** | Служит для отображения подарков к конкретному товару. |
| [Генерация купона на товар для почты](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_discount_coupon_mail.php) | **sale.discount.coupon.mail** | Генерирует купон для правила корзины с соответствии с заданными параметрами |
| [Персональные рекомендации для почты](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_bigdata_personal_mail.php) | **sale.discount.coupon.mail** | Выводит список рекомендованных товаров для почты |
| [Самые продаваемые товары](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_bestsellers.php) | **sale.bestsellers** | Выводит список самых продаваемых товаров |
| [Сопутствующие заказу товары для почты](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_bigdata_followup_mail.php) | **sale.bigdata.followup.mail** | Выводит товары, сопутствующие ранее заказанным товарам |
| [С этим товаром покупают](https://dev.1c-bitrix.ru/user_help/components/magazin/information_tovars/sale_recommended_products.php) | **sale.recommended.products** | Выводит товары, которые были куплены вместе с просматриваемым товаром, с учетом минимального количества покупок |

Новинки документации в соцсетях:

© «Битрикс», 2001-2025, «1С-Битрикс», 2025

Наверх