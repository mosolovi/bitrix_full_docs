[Подписка, рассылки](/api_help/subscribe/index.php)

События (доступен с 6.0.1)

События
=======

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [BeforePostingSendMail](/api_help/subscribe/events/beforepostingsendmail.php) | перед отправкой выпуска каждому конкретному адресату. | CPostingGeneral::SendMessage | 6.0.1 |
| OnEventMessageDelete | при удалении сообщения. | subscribe::UnInstallDB | 6.5.4 |
| OnBeforeSubscriptionDelete | перед удалением подписки. | CSubscriptionGeneral::Delete | 14.5.1 |
| OnAfterSubscriptionDelete | после удаления подписки. | CSubscriptionGeneral::Delete | 14.5.1 |
| OnStartSubscriptionUpdate | при обновлении подписки. | CSubscriptionGeneral::CheckFields | 14.5.1 |
| OnBeforeSubscriptionUpdate | перед обновлением подписки. | CSubscriptionGeneral::CheckFields | 14.5.1 |
| OnStartSubscriptionAdd | при добавлении подписки. | CSubscriptionGeneral::CheckFields | 14.5.1 |
| OnBeforeSubscriptionAdd | перед добавлением подписки. | CSubscriptionGeneral::CheckFields | 14.5.1 |

Новинки документации в соцсетях: