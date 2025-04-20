[Push and Pull](/api_help/push_pull/index.php)

[События](/api_help/push_pull/events/index.php)

События модуля Push and Pull

События модуля Push and Pull
============================

| Метод | Описание | С версии |
| --- | --- | --- |
| onPullOnlineEvent | Событие для получения данных об онлайне. | 14.1.0 |

Cобытия и push-уведомления отправляются на серверы рассылки в эпилоге страницы. Если вы отправляете события в ajax-обработчиках, вам обязательно необходимо использовать `CMain::FinalActions()` в финале обработчика.

**Примечание**: если в объекте события будет найден объект времени [\Main\Type\DateTime](https://dev.1c-bitrix.ru/api_d7/bitrix/main/type/datetime/index.php), клиент от сервера Push & Pull получит дату в формате ATOM.

Новинки документации в соцсетях: