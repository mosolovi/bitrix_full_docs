[Интранет](/api_help/intranet/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание и параметры

Компоненты 2.0

### Описание и параметры

Модуль **Интранет** позволяет:

* указать источники данных для компонентов модуля;
* настроить параметры импорта пользователей из 1С:ЗУП;
* настроить параметры поиска документов.

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?    
if(CModule::IncludeModule("intranet"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

### Компоненты 2.0

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Руководство подразделениями](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_structure_head_user.php) | **intranet.structure.head.user** | Выводит список подразделений, руководителем которых является сотрудник. |
| **HR** | | |
| [Календарь отсутствий](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_absence_calendar.php) | **intranet.absence.calendar** | Выводит график отсутствий сотрудников в виде календаря. |
| [Отсутствия пользователя](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_absence_user.php) | **intranet.absence.user** | Выводит график отсутствий конкретного пользователя. |
| [Дни рождения](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_birthday_nearest.php) | **intranet.structure.birthday.nearest** | Выводит список ближайших именинников офиса, отдела или филиала компании. |
| [Кадровые изменения](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_events.php) | **intranet.structure.events** | Выводит список последних кадровых перестановок в компании. |
| [Доска почета](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_honour.php) | **intranet.structure.honour** | Выводит список почетных сотрудников компании. |
| [Доска почета пользователя](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_honour_user.php) | **intranet.structure.honour.user** | Выводит историю присутствия пользователя на доске почета. |
| [Отсутствующие сотрудники](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_informer_absent.php) | **intranet.structure.informer.absent** | Выводит краткий список отсутствующих сотрудников. |
| [Новые сотрудники](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_user/intranet_structure_informer_new.php) | **intranet.structure.informer.new** | Выводит краткий список новых сотрудников компании. |
| **Бронирование переговорных** | | |
| [Бронирование переговорных (комплексный компонент)](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting.php) | **intranet.reserve\_meeting** | Выводит календарь занятости переговорных комнат, позволяет бронировать переговорные и управлять ими. |
| [Создание переговорной](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_add.php) | **intranet.reserve\_meeting.add** | Служит для создания переговорной комнаты. |
| [Список переговорных](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_list.php) | **intranet.reserve\_meeting.list** | Выводит список переговорных. |
| [Переговорная](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_meeting.php) | **intranet.reserve\_meeting.meeting** | Служит для отображения переговорной. |
| [Меню](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_menu.php) | **intranet.reserve\_meeting.menu** | Выводит меню комплексного компонента. |
| [Резервирование переговорной](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_reserve.php) | **intranet.reserve\_meeting.reserve** | Служит для резервирования переговорной. |
| [Поиск переговорных](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/reserve_meeting/intranet_reserve_meeting_search.php) | **intranet.reserve\_meeting.search** | Служит для поиска переговорных. |
| [Просмотр резервирования](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_reserve/intranet_reserve_meeting_view_item.php) | **intranet.reserve\_meeting.view\_item** | Предназначен для просмотра резервирования переговорных. |
| **Оргструктура** | | |
| [Поиск сотрудника (комплексный компонент)](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_search/intranet_search.php) | **intranet.search** | Выводит форму поиска и список найденных сотрудников корпоративного портала. |
| [Структура компании (комплексный компонент)](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_search/intranet_structure.php) | **intranet.structure** | Выводит дерево структуры компании со списком сотрудников корпоративного портала. |
| [Список сотрудников](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_search/intranet_structure_list.php) | **intranet.structure.list** | Выводит список сотрудников, удовлетворяющих внешнему фильтру. |
| [Форма поиска](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_search/intranet_structure_selector.php) | **intranet.structure.selector** | Выводит форму фильтрации списка сотрудников. |
| [Визуальная структура компании](http://dev.1c-bitrix.ru/user_help/components/intranet/intranet_search/intranet_structure_visual.php) | **intranet.structure.visual** | Выводит визуальное представление древовидной структуры компании. |
| **Собрания и планерки** | | |
| [Собрания и планерки](http://dev.1c-bitrix.ru/user_help/components/intranet/meetings/meetings.php) | **meetings** | Комплексный компонент для управления собраниями. |
| **Системные (не описываются)** | | |
| Начало работы с Bitrix24Time | **faceid.timeman.start** | Включает Bitrix24Time и запускает индексацию фотографий сотрудников. |
| Фейс-трекер рабочего времени | **faceid.timeman** | Автоматизирует открытие и закрытие рабочего дня по фотографии пользователя. |
| Отчет по рабочему времени | **timeman.report** | Вывод отчета по рабочему времени для сотрудников и руководителей. |
| Отчеты по работе сотрудников | **timeman.report.weekly** | Вывод отчетов по работе сотрудников и руководителей. |
| Учет рабочего времени | **timeman** | Основной инструментарий учета рабочего времени. |

Новинки документации в соцсетях: