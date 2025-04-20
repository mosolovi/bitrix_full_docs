CRM

CRM
===

Включить вкладки

Компании

Контакты

Лиды

Настройки

Сделки

Действия

Счета

Товары

Дополнительно

Модуль включает в себя следующие Компоненты 2.0:

Перед использованием модуля необходимо проверить, установлен ли он, и подключить его при помощи конструкции:

```
<? 
if(CModule::IncludeModule("crm"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

### Компании

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Компании (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_company/crm_company.php) | **crm.company** | Позволяет управлять списком компаний. |
| [Список компаний](https://dev.1c-bitrix.ru/user_help/components/crm/crm_company/crm_company_list.php) | **crm.company.list** | Выводит список компаний. |
| [Редактирование компании](https://dev.1c-bitrix.ru/user_help/components/crm/crm_company/crm_company_edit.php) | **crm.company.edit** | Позволяет добавлять новую, или редактировать параметры имеющейся компании. |
| [Просмотр компании](https://dev.1c-bitrix.ru/user_help/components/crm/crm_company/crm_company_view.php) | **crm.company.show** | Осуществляет вывод детального описания компании. |
| [Панель инструментов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_company/crm_company_menu.php) | **crm.company.menu** | Позволяет настроить верхнее меню сущности. |
| Импорт компаний\* | **crm.company.menu** | Позволяет импортировать список компаний. |
| \* отмечены системные компоненты (не описываются) | | |

### Контакты

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Контакты (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm.contact/crm_contact.php) | **crm.contact** | Позволяет управлять списком контактов. |
| [Список контактов](https://dev.1c-bitrix.ru/user_help/components/crm/crm.contact/crm_contact_list.php) | **crm.contact.list** | Выводит список контактов. |
| [Редактирование контакта](https://dev.1c-bitrix.ru/user_help/components/crm/crm.contact/crm_contact_edit.php) | **crm.contact.edit** | позволяет добавлять новый, или редактировать параметры имеющегося контакта. |
| [Просмотр контакта](https://dev.1c-bitrix.ru/user_help/components/crm/crm.contact/crm_contact_show.php) | **crm.contact.show** | Осуществляет вывод детального описания контакта. |
| [Панель инструментов](https://dev.1c-bitrix.ru/user_help/components/crm/crm.contact/crm_contact_menu.php) | **crm.contact.menu** | Позволяет настроить верхнее меню сущности. |
| Экспорт\* | **crm.contact.export** | Предназначен для экспорта контактов в формате **.xml**. |
| Импорт контактов\* | **crm.contact.import** | Предназначен для импорта списка контактов в формате **CSV**. |
| Импорт сделок\* | **crm.deal.import** | Предназначен для импорта списка сделок в формате **CSV**. |
| Веб сервис\* | **crm.contact.webservice** | Предназначен для создания и экспорта контактов. |
| \* отмечены системные компоненты (не описываются) | | |

### Лиды

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Лиды (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead.php) | **crm.lead** | Позволяет работать с лидами. |
| [Список лидов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead_list.php) | **crm.lead.list** | Выводит список лидов. |
| [Редактирование лида](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead_edit.php) | **crm.lead.edit** | Позволяет создать новый, либо редактировать существующий лид. |
| [Просмотр лида](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead_show.php) | **crm.lead.show** | Осуществляет вывод детального описания лида. |
| [Туллбар](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead_menu.php) | **crm.lead.menu** | Позволяет настроить верхнее меню сущности. |
| [Конвертация лида](https://dev.1c-bitrix.ru/user_help/components/crm/crm_lead/crm_lead_convert.php) | **crm.lead.convert** | Позволяет конвертировать лид в контакт, компанию или сделку. |
| Импорт лидов\* | **crm.lead.import** | Предназначен для импорта списка лидов в формате **CSV**. |
| Веб-сервис\* | **crm.lead.webservice** | Сервис для создания лида. |
| Обработчик REST\* | **crm.lead.rest** | Обработчик REST для создания лида. |
| \* отмечены системные компоненты (не описываются) | | |

### Настройки

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Настройки пользовательских полей (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_config/crm_config_fields.php) | **crm.config.fields** | Позволяет выполнить настройку пользовательских полей в модуле CRM. |
| [Список пользовательских полей](https://dev.1c-bitrix.ru/user_help/components/crm/crm_config/crm_config_fields_list.php) | **crm.config.fields.list** | Выводит список пользовательских полей модуля CRM. |
| [Список типов пользовательских полей](https://dev.1c-bitrix.ru/user_help/components/crm/crm_config/crm_config_fields_types.php) | **crm.config.fields.types** | Выводит список типов пользовательских полей модуля CRM. |
| [Настройка пользовательского поля](https://dev.1c-bitrix.ru/user_help/components/crm/crm_config/crm_config_fields_edit.php) | **crm.config.fields.edit** | Позволяет выполнить настройку пользовательского поля модуля CRM. |
| [Настройки прав доступа (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_config/access_config.php) | **crm.config.perms** | Позволяет выполнить настройку прав доступа к модулю CRM. |
| Настройка Send&Save\* | **crm.config.sendsave** | Настройка интеграции с Send&Save в модуле CRM. |
| Настройка статусов\* | **crm.config.status** | Позволяет выполнить настройку статусов модуля CRM. |
| \* отмечены системные компоненты (не описываются) | | |

### Сделки

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Сделки (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/crm_deal.php) | **crm.deal** | Позволяет работать со сделками. |
| [Воронка продаж](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/voronka.php) | **crm.deal.funnel** | Выводит количественное соотношение сделок на разных стадиях выполнения. |
| [Список сделок](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/crm_deal_list.php) | **deal.list** | Выводит список сделок. |
| [Редактирование сделки](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/crm_deal_edit.php) | **crm.deal.edit** | Позволяет создать новую, либо редактировать существующую сделку. |
| [Просмотр сделки](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/crm_deal_show.php) | **crm.deal.show** | Осуществляет вывод детального описания сделки. |
| [Панель инструментов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_deal/crm_deal_menu.php) | **crm.deal.menu** | Позволяет настроить верхнее меню сущности. |

### Действия

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Дела (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_activity/crm_activity.php) | **crm.activity.calendar.list** | Выводит список записей календаря. |
| [Список задач](https://dev.1c-bitrix.ru/user_help/components/crm/crm_activity/task_list.php) | **crm.activity.task.list** | Выводит список задач. |
| [Список звонков/встреч](https://dev.1c-bitrix.ru/user_help/components/crm/crm_activity/activity_calendar_list.php) | **crm.activity.calendar.list** | Выводит список записей календаря. |

### Счета

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Счета (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_invoice/crm_invoice.php) | **crm.invoice** | Позволяет работать со счетами в CRM. |
| [Список счетов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_invoice/invoice_list.php) | **crm.invoice.list** | Выводит список счетов. |
| [Редактирование счета](https://dev.1c-bitrix.ru/user_help/components/crm/crm_invoice/crm_invoice_edit.php) | **crm.invoice.edit** | Добавляет новый, или позволяет редактировать параметры имеющегося счёта. |
| [Просмотр счета](https://dev.1c-bitrix.ru/user_help/components/crm/crm_invoice/invoice_show.php) | **crm.invoice.show** | Выводит детальное описание счёта. |
| [Панель инструментов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_invoice/invoice_menu.php) | **crm.invoice.menu** | Позволяет настроить контентное меню сущности. |
| Просмотр счета в формате HTML/PDF\* | **crm.invoice.payment** | Просмотр счета в формате HTML/PDF. |
| \* отмечены системные компоненты (не описываются) | | |

### Товары

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Товары (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/crm_product.php) | **crm.product** | Позволяет управлять товарами сделок CRM. |
| [Список товаров](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/product_list.php) | **crm.product.list** | Выводит список товаров системы CRM. |
| [Список разделов](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/product_section.php) | **crm.product.section.list** | Позволяет управлять списком разделов выбранного каталога. |
| [Редактирование товара](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/product_edit.php) | **crm.product.edit** | Позволяет редактировать существующий, либо добавить новый товар. |
| [Просмотр товара](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/product_show.php) | **crm.product.show** | Выводит детальное описание товара. |
| [Туллбар](https://dev.1c-bitrix.ru/user_help/components/crm/crm_product/product_menu.php) | **crm.product.menu** | Позволяет настроить контентное меню для работы с каталогами и товарами. |

### Дополнительно

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Просмотр событий](https://dev.1c-bitrix.ru/user_help/components/crm/event_view.php) | **crm.event.view** | Выводит список действий, произведенных над сущностями системы CRM. |
| [Отчеты (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/crm/crm_report.php) | **crm.report** | Составляет отчеты по работе в CRM. |
| [Просмотр событий счета](https://dev.1c-bitrix.ru/user_help/components/crm/invoice_events.php) | **crm.invoice.events** | Выводит список действий, произведенных над счетами системы CRM. |
| \* отмечены системные компоненты (не описываются) | | |

Новинки документации в соцсетях: