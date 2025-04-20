[Push and Pull](/api_help/push_pull/index.php)

[Классы](/api_help/push_pull/classes/index.php)

CPullWatch (11.5.0)

CPullWatch
==========

Класс осуществляет отправку данных подписанным пользователям.

**ВНИМАНИЕ**: в целях безопасности, пользователи не имеют возможности подписыватся на канал через JS, что бы, например, не читать чужую закрытую статью и т.д. Поэтому в теге подписки нельзя использовать параметры из **$\_GET**, **$\_POST**, **$\_REQUEST**, чтобы злоумышленник не смог подписаться на контент который ему запрещен.

| Метод | Описание | С версии |
| --- | --- | --- |
| [Add](/api_help/push_pull/classes/cpullwatch/add.php) | Подписка на команды. |  |
| [Delete](/api_help/push_pull/classes/cpullwatch/delete.php) | Удаление подписки. | 12.5.5 |
| [AddToStack](/api_help/push_pull/classes/cpullwatch/addtostack.php) | Отправка данных подписанным пользователям. |  |
| [GetUserList](/api_help/push_pull/classes/cpullwatch/getuserlist.php) | Получение списка пользователей, подписанных на определённый тег. |  |

Новинки документации в соцсетях: