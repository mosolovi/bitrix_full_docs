[Техподдержка](/api_help/support/index.php)

Для разработчиков

Для разработчиков
=================

Информация, представленная в данном разделе, содержит сведения о классах и методах классов модуля **Техподдержка**, а также об этапах инсталляции модуля.

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<? 
if(CModule::IncludeModule("support"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Мастер создания обращения](https://dev.1c-bitrix.ru/user_help/components/services/support/iblock_wizard.php) | **iblock.wizard** | Формирует разделы мастера на основе секций инфоблока и вопросы на основе элементов инфоблока. |
| [FAQ (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/services/faq/support_faq.php) | **support.faq** | Выводит FAQ категории и вопросы из инфоблока. |
| [Вопрос FAQ](https://dev.1c-bitrix.ru/user_help/components/services/faq/support_faq_element_detail.php) | **support.faq.element.detail** | Выводит один вопрос FAQ из инфоблока конкретной категории. |
| [Список вопросов FAQ из секции](https://dev.1c-bitrix.ru/user_help/components/services/faq/support_faq_element_list.php) | **support.faq.element.list** | Выводит вопросы FAQ из инфоблока. |
| [Список категорий FAQ](https://dev.1c-bitrix.ru/user_help/components/services/faq/support_faq_section_list.php) | **support.faq.section.list** | Выводит список категории FAQ из инфоблока. |
| [Техподдержка (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/services/support/support_ticket.php) | **support.ticket** | Создает полноценную систему техподдержки, с помощью которой можно просмотреть список обращений, добавить своё сообщение или написать новое обращение в техподдержку. |
| [Создание нового, либо редактирование существующего обращения](https://dev.1c-bitrix.ru/user_help/components/services/support/support_ticket_edit.php) | **support.ticket.edit** | Предназначен для вывода формы редактирования существующего обращения либо создания нового. |
| [Список обращений](https://dev.1c-bitrix.ru/user_help/components/services/support/support_ticket_list.php) | **support.ticket.list** | Предназначен для вывода формы фильтра и списка обращений в техподдержку. |
| [Техподдержка с мастером (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/services/support/support_wizard.php) | **support.wizard** | Служит для организации полноценного публичного интерфейса технической поддержки, создание обращения в котором выполняется с помощью специального мастера. |

Новинки документации в соцсетях: