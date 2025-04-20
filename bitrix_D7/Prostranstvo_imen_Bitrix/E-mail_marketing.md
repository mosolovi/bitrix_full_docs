[Пространство имён Bitrix](/api_d7/bitrix/index.php)

[E-mail маркетинг](/api_d7/bitrix/sender/index.php)

E-mail Маркетинг

E-mail Маркетинг
================

Раздел содержит информацию о классах модуля **E-mail Маркетинг**, относящихся к ядру D7 и находящихся соответственно в пространстве имен `\Bitrix\Sender`.

Перед использованием модуля необходимо проверить, установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule('sender');
Копировать
```

| Класс | Описание |
| --- | --- |
| [ConnectorManager](/api_d7/bitrix/sender/connectormanager/index.php) | Класс для работы с коннекторами. |
| [ContactTable](/api_d7/bitrix/sender/contacttable/index.php) | Класс для работы c таблицей контактов получателей рассылки. |
| [GroupTable](/api_d7/bitrix/sender/grouptable/index.php) | Класс для работы с таблицей групп адресов для рассылки. |
| [ListTable](/api_d7/bitrix/sender/listtable/index.php) | Класс для работы с таблицей списка адресов рассылки. |
| MailingChainTable | Класс для работы с таблицей выпусков рассылки. Устарел с 18.0.0. |
| [MailingSubscriptionTable](/api_d7/bitrix/sender/mailingsubscriptiontable/index.php) | Класс для работы c таблицей подписок на рассылку. |
| MailingTable | Класс для работы с таблицей рассылок. Устарел с версии 18.0.0. |
| [PostingClickTable](/api_d7/bitrix/sender/postingclicktable/index.php) | Класс для работы с таблицей переходов из письма. |
| [PostingManager](/api_d7/bitrix/sender/postingmanager/index.php) | Класс для работы с выпусками рассылок. |
| [PostingReadTable](/api_d7/bitrix/sender/postingreadtable/index.php) | Класс для работы с таблицей прочтения писем. |
| [PostingRecipientTable](/api_d7/bitrix/sender/postingrecipienttable/index.php) | Класс для работы с получателями сообщений. |
| [PostingTable](/api_d7/bitrix/sender/postingtable/index.php) | Класс для работы с таблицами рассылок. |
| [PostingUnsubTable](/api_d7/bitrix/sender/postingunsubtable/index.php) | Класс для работы отписок от рассылки. |
| [SenderConnectorUnSubscribers](/api_d7/bitrix/sender/senderconnectorunsubscribers/index.php) | Класс для работы с коннекторами отписавшихся от рассылки пользователей. |
| [Subscription](/api_d7/bitrix/sender/subscription/index.php) | Класс для работы c подписками. |
| [TemplateTable](/api_d7/bitrix/sender/templatetable/index.php) | Класс для работы c таблицей шаблонов сообщения рассылки. |
| [TriggerConnector](/api_d7/bitrix/sender/triggerconnector/index.php) | Класс для работы с коннекторами триггерных рассылок. |
| [TriggerManager](/api_d7/bitrix/sender/triggermanager/index.php) | Класс для работы с триггерными рассылками. |

  

#### Смотрите также

* [Модуль Email-маркетинг](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=139&CHAPTER_ID=011235)
* [Настройки модуля Email-маркетинг](https://dev.1c-bitrix.ru/user_help/marketing/sender/settings_email_marketing.php)

Новинки документации в соцсетях: