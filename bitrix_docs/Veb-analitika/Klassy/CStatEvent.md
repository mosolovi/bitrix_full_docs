[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

Класс CStatEvent (С версии 8.6.3)

Класс CStatEvent
================

**CStatEvent** - класс для работы с [событиями](/api_help/statistic/terms.php#event).

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [Add](/api_help/statistic/classes/cstatevent/add.php) | Добавляет событие по заданному ID [типа события](/api_help/statistic/terms.php#event_type) и [специальному параметру](/api_help/statistic/terms.php#gid). |  |
| [AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php) | Добавляет событие по заданным [идентификаторам](/api_help/statistic/terms.php#event_type_id) типа события и [специальному параметру](/api_help/statistic/terms.php#gid). |  |
| [AddCurrent](/api_help/statistic/classes/cstatevent/addcurrent.php) | Добавляет событие используя текущие параметры [посетителя](/api_help/statistic/terms.php#guest). |  |
| [DecodeGid](/api_help/statistic/classes/cstatevent/decodegid.php) | Декодирует [специальный параметр](/api_help/statistic/terms.php#gid) используемый при создании события. |  |
| [Delete](/api_help/statistic/classes/cstatevent/delete.php) | Удаляет указанное событие. |  |
| [GetGID](/api_help/statistic/classes/cstatevent/getgid.php) | Возвращает [специальный параметр](/api_help/statistic/terms.php#gid) для текущего посетителя. |  |
| [GetHandlerList](/api_help/statistic/classes/cstatevent/gethandlerlist.php) | Возвращает список доступных [обработчиков CSV файлов](/api_help/statistic/terms.php#handler) для вывода его в выпадающем списке с помощью функции [SelectBoxFromArray](/api_help/main/functions/html/selectboxfromarray.php), либо в списке множественного выбора с помощью функции [SelectBoxMFromArray](/api_help/main/functions/html/selectboxmfromarray.php). |  |
| [GetList](/api_help/statistic/classes/cstatevent/getlist.php) | Возвращает список событий. |  |
| [GetListByGuest](/api_help/statistic/classes/cstatevent/getlistbyguest.php) | Возвращает список событий по указанному ID посетителя сайта. |  |

#### Смотрите также

* Пользовательскую документацию, [отчет "Список событий"](http://www.1c-bitrix.ru/user_help/statistic/events/event_list.php)

Новинки документации в соцсетях: