[Пространство имён Bitrix](/api_d7/bitrix/index.php)

CRM

CRM
===

Раздел содержит информацию о классах модуля **CRM**, относящихся к ядру D7 и находящихся соответственно в пространстве имен **\Bitrix\Crm**.

Базовые методы сущностей:

* **CCrmLead** - лиды,
* **CCrmDeal** - сделки,
* **CCrmCompany** - компании,
* **CCrmContact** - контакты,
* **CCrmQuote** - предложения,
* **CCrmInvoice** - счета.

Классы CCrmQuote и CCrmInvoice не имеют методов getListEx, но имеют полностью аналогичный getList.

Перед использованием модуля необходимо проверить установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule('crm');
Копировать
```

| Класс, пространство имён | Описание |
| --- | --- |
| [Activity](/api_d7/bitrix/crm/activity/index.php) | Пространство имён содержит классы для работы с делами в CRM. |
| [Automation](/api_d7/bitrix/crm/automation/index.php) | Пространство имён cодержит классы для автоматизации продаж в CRM. |
| [BankDetailTable](/api_d7/bitrix/crm/bankdetailtable/index.php) | Класс предназначен для работы с банковскими реквизитами. |
| [Binding](/api_d7/bitrix/crm/binding/index.php) | Пространство имён классов для множественных привязок сущностей CRM. |
| [CallList](/api_d7/bitrix/crm/calllist/index.php) | Подпространство имён содержит классы для работы со звонками. |
| [Category](/api_d7/bitrix/crm/category/index.php) | Пространство имён классов для работы с Направлениями. |
| [Color](/api_d7/bitrix/crm/color/index.php) | Пространство имён классов для хранения цветовых схем стадий Сделки, статусов Лида и Предложения в CRM. |
| [CommunicationType](/api_d7/bitrix/crm/communicationtype/index.php) | класс для работы с типами связей. |
| [CompanyAddress](/api_d7/bitrix/crm/companyaddress/index.php) | Класс для хранения адресов Компаний. |
| [Config](/api_d7/bitrix/crm/config/index.php) | Пространство имён классов для хранения пользовательских настроек в контексте определенной сущности. |
| [ContactAddress](/api_d7/bitrix/crm/contactaddress/index.php) | Класс для хранения адресов Контактов. |
| [Conversion](/api_d7/bitrix/crm/conversion/index.php) | Пространство имён классов для конвертации сущностей CRM. |
| [Entity](/api_d7/bitrix/crm/entity/index.php) | Пространство имён содержит классы для работы с сущностями. |
| [EntityAddress](/api_d7/bitrix/crm/entityaddress/index.php) | Класс для хранения адресов сущностей. |
| [EntityBankDetail](/api_d7/bitrix/crm/entitybankdetail/index.php) | Класс для работы с банковскими реквизитами. |
| [EntityRequisite](/api_d7/bitrix/crm/entityrequisite/index.php) | Класс для работы с реквизитами сущности. |
| [Entry](/api_d7/bitrix/crm/entry/index.php) | Пространство имён содержит классы для хранения отдельных записей. |
| [Integration](/api_d7/bitrix/crm/integration/index.php) | Пространство имён классов для для взаимодействия с другими модулями - интеграции. |
| [Integrity](/api_d7/bitrix/crm/integrity/index.php) | Пространство имён содержит классы для контроля, поиска, отслеживания и объединения дубликатов. |
| [InvoiceTable](/api_d7/bitrix/crm/invoicetable/index.php) | Класс предназначен для работы с таблицей счетов. |
| [Kanban](/api_d7/bitrix/crm/kanban/index.php) | Пространство имён содержит классы для работы с канбаном. |
| [LeadAddress](/api_d7/bitrix/crm/leadaddress/index.php) | Класс для хранения адресов Лидов. |
| [Merger](/api_d7/bitrix/crm/merger/index.php) | Пространство имён классов, используемых при управлении дубликатами, при конвертации и для объединения полей сущностей. |
| [PresetTable](/api_d7/bitrix/crm/presettable/index.php) | Класс ORM для работы с шаблонами реквизитов CRM. |
| [Preview](/api_d7/bitrix/crm/preview/index.php) | Пространство имён классов, используемых при формировании "богатых ссылок" на сущности CRM. |
| [Requisite](/api_d7/bitrix/crm/requisite/index.php) | Пространство имён классов, используемых для конвертации реквизитов из сущностей. |
| [RequisiteAddress](/api_d7/bitrix/crm/requisiteaddress/index.php) | Класс для хранения адресов реквизитов. |
| [RequisiteTable](/api_d7/bitrix/crm/requisitetable/index.php) | Класс для работы с реквизитами сущностей. |
| [Restriction](/api_d7/bitrix/crm/restriction/index.php) | Пространство имён содержит классы для работы с ограничениями. |
| [Settings](/api_d7/bitrix/crm/settings/index.php) | Пространство имён классов и методов для выполнения различных неосновных настроек системы CRM. |
| [Statistics](/api_d7/bitrix/crm/statistics/index.php) | Пространство имён классов, используемых для сбора данных для построения аналитических отчетов. |
| [Synchronization](/api_d7/bitrix/crm/synchronization/index.php) | Пространство имён классов, используемых для синхронизации наборов пользовательских полей между различными типами сущностей. |
| [Widget](/api_d7/bitrix/crm/widget/index.php) | Виджеты, используемые для построения аналитических отчётов. |

Новинки документации в соцсетях: