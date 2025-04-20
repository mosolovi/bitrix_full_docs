[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Класс CSubscriptionGeneral (доступен с 3.0.5)

Класс CSubscriptionGeneral
==========================

**CSubscriptionGeneral** - класс для работы с подписками на рассылки.

#### Методы класса

| Метод | Описание | C версии |
| --- | --- | --- |
| [Add](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptionadd.php) | Метод добавляет подписку на рассылки и отправляет подписчику письмо с кодом подтверждения подписки (если не указано не отправлять). | 3.0.5 |
| [Authorize](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptionauthorize.php) | Авторизует посетителя для доступа к редактированию подписки. Признак успешной авторизации сохраняется в PHP-сессии. | 3.3.2 |
| [ConfirmEvent](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptionconfirmevent.php) | Метод добавляет событие SUBSCRIBE\_CONFIRM для отправки подписчику письма с кодом подтверждения подписки. Письмо формируется по шаблону типа "SUBSCRIBE\_CONFIRM - Подтверждение подписки". | 3.0.5 |
| [Delete](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiondelete.php) | Метод удаляет подписку. | 3.0.5 |
| [GetByID](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongetbyid.php) | Метод выбирает подписку по ее идентификатору. | 3.0.5 |
| [GetList](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongetlist.php) | Метод выбирает список подписок по фильтру. | 3.0.5 |
| [GetRubricArray](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongetrubricarray.php) | Метод возвращает массив идентификаторов рассылок, на которые подписан данный адрес. | 3.0.5 |
| [GetRubricList](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongetrubriclist.php) | Метод возвращает выборку рассылок, на которые подписан данный адрес. | 3.0.5 |
| [GetUserSubscription](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongetusersubscription.php) | Метод возвращает массив полей подписки текущего пользователя. Подписка определяется по Email, сохраненному в куках посетителя, либо по Email авторизованного пользователя. | 3.0.5 |
| [IsAuthorized](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptionisauthorized.php) | Метод проверяет, авторизован ли текущий посетитель для доступа к информации о подписке. | 3.3.2 |
| [Update](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptionupdate.php) | Метод изменяет данные подписки. Если изменяется адрес подписки, то Метод снимает подтверждение с подписки и генерирует событие для отправки письма с кодом подтверждения подписки (если это явно не запрещено). Если подписка не подтверждена, а массив полей включает в себя правильный CONFIRM\_CODE, то подписка подтверждается. | 3.0.5 |

Новинки документации в соцсетях: