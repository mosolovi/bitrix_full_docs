[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Поля CSubscriptionGeneral

Поля CSubscriptionGeneral
=========================

Класс CSubscriptionGeneral использует следующие поля при работе с объектом "Подписка":

| Название поля | Описание | Тип | Обяз. |
| --- | --- | --- | --- |
| ID | Идентификатор подписки. | int | Да. |
| DATE\_INSERT | Дата добавления записи. | datetime |  |
| DATE\_UPDATE | Дата модификации записи. | datetime |  |
| USER\_ID | Идентификатор пользователя, которому принадлежит подписка. Если NULL, то подписка анонимна. | int |  |
| ACTIVE | Признак активности подписки (Y/N). Если подписка не активна, то рассылка на этот адрес не производится. | char(1) |  |
| EMAIL | Email подписки (уникальный). | string(255) | Да. |
| FORMAT | Предпочтительный формат выпуска (text/html). | string(4) |  |
| CONFIRM\_CODE | Код подтверждения подписки (пароль). | string(8) |  |
| CONFIRMED | Признак подтверждения подписки (Y/N). | char(1) |  |
| DATE\_CONFIRM | Дата отправки кода подтверждения подписки. | datetime |  |

Новинки документации в соцсетях: