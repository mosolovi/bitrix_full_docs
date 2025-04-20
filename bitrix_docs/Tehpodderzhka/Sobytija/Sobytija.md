[Техподдержка](/api_help/support/index.php)

События

События
=======

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| OnBeforeTicketNotify | Перед отсылкой уведомления о необходимости ответа на обращение. | CTicketReminder::SupportDeadlineNotify | 12.5.1 |
| OnBeforeTicketExpire | Перед установкой статуса "Просрочен" у обращений. | CTicketReminder::SupportDeadline | 12.5.1 |
| OnAfterUseCoupon | После использования купона. | CSupportSuperCoupon::UseCoupon | 7.0.5 |
| OnBeforeSendCouponEMail | Перед пересылкой купона по e-mail. | CSupportSuperCoupon::UseCoupon | 7.0.5 |
| OnBeforeTicketAdd | Перед добавлением тикета. | [CTicket::Set](/api_help/support/classes/cticket/set.php) | 9.1.0 |
| OnBeforeTicketDelete | Перед удалением тикета. | [CTicket::Delete](/api_help/support/classes/cticket/delete.php) | 9.1.0 |
| OnBeforeTicketUpdate | Перед изменением тикета. При подписке на это событие функция должна отдавать результатом `arFields`:    ``` function OnBeforeTicketUpdate($arFields) {     // ваш код     return $arFields; }Копировать ``` | [CTicket::Set](/api_help/support/classes/cticket/set.php) | 9.1.0 |
| OnTicketDelete | При удалении тикета. | [CTicket::Delete](/api_help/support/classes/cticket/delete.php) | 9.1.0 |
| OnAfterTicketAdd | После добавления тикета. | [CTicket::Set](/api_help/support/classes/cticket/set.php) | 8.0.1 |
| OnAfterTicketUpdate | После изменения тикета. | [CTicket::Set](/api_help/support/classes/cticket/set.php) | 8.0.1 |
| [OnBeforeSendMailToAuthor](/api_help/support/support_events/onbeforesendmailtoauthor.php) | Перед отправкой письма клиенту модуля **Тех. поддержка**. | CTicket::Set\_sendMails | 7.0.0 |
| [OnBeforeSendMailToSupport](/api_help/support/support_events/onbeforesendmailtosupport.php) | Перед отправкой письма сотруднику модуля **Тех. поддержка**. | CTicket::Set\_sendMails | 7.0.0 |
| OnAfterSendCouponEMail | После пересылки купона по e-mail. | CSupportSuperCoupon::UseCoupon | 7.0.4 |
| OnBeforeUseCoupon | Перед использованием купона. | CSupportSuperCoupon::UseCoupon | 7.0.4 |

Новинки документации в соцсетях: