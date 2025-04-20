[Социальная сеть](/api_help/socialnetwork/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Компоненты 2.0

### Описание

Модуль **Социальная сеть** предоставляет следующие возможности:

- создание персонального профайла пользователя с возможностью его редактирования;
  
- настройка прав на доступ к содержимому личной страницы;
  
- создание произвольного числа рабочих групп;
  
- настройка прав на доступ к группе и содержимому ее страницы;
  
- форумы, блоги, календари, фотогалереи и файлы сотрудников и рабочих групп;
  
- классификация и поиск групп.

[Классы модуля](/api_help/socialnetwork/classes/index.php)
  
[События модуля](/api_help/socialnetwork/events/index.php)

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?
if(CModule::IncludeModule("socialnetwork"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

### Компоненты 2.0

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Социальная сеть (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet.php) | **socialnetwork** | Создает полноценный публичный интерфейс социальной сети. |
| [Социальная сеть - группы (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group.php) | **socialnetwork\_group** | Служит для создания раздела рабочих групп социальной сети. |
| [Социальная сеть - пользователь (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user.php) | **socialnetwork\_user** | Служит для создания личного раздела пользователя социальной сети. |
| [Меню сообщений](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_blog_menu.php) | **socialnetwork.blog.menu** | Выводит меню сообщений социальной сети. |
| [Список последних тем](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_forum_topic_last.php) | **socialnetwork.forum.topic.last** | Выводит список последних тем форума пользователя или рабочей группы социальной сети. |
| [Тема (создание)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_forum_topic_new.php) | **socialnetwork.forum.topic.new** | Служит для сохранения новой темы форума социальной сети.. |
| [Тема (чтение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_forum_topic_read.php) | **socialnetwork.forum.topic.read** | Выводит список сообщений темы форума социальной сети. |
| [Темы (список)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_forum_topic_list.php) | **socialnetwork.forum.topic.list** | Выводит список всех тем форума социальной сети. |
| [Форма ввода пользователей](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_search_input.php) | **socialnetwork.user\_search\_input** | Выводит форму, с помощью которой осуществляется ввод пользователей социальной сети. |
| [Форма создания сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_forum_post_form.php) | **socialnetwork.user\_search\_input** | Выводит форму создания сообщения (или темы) форума социальной сети. |
| [Сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_blog_blog.php) | **socialnetwork.blog.blog** | Выводит сообщения блога социальной сети с возможностью их фильтрации по категории и дате. |
| [Сообщения - модерация](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_blog_moderation.php) | **socialnetwork.blog.moderation** | Выводит сообщения, требующие модерации. |
| [Черновики сообщений](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_blog_draft.php) | **socialnetwork.blog.draft** | Выводит черновики сообщений. |
| [Сообщение детально](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_blog_post.php) | **socialnetwork.blog.post** | Выводит подробно сообщение. |
| [Комментарии к сообщению](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_blog_post_comment.php) | **socialnetwork.blog.post.comment** | Выводит комментарии к сообщению с возможностью добавления. |
| [Изменение профиля пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_profile_edit.php) | **socialnetwork.user\_profile\_edit** | Позволяет изменить данные профиля пользователя социальной сети. |
| [Просмотр профиля пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_profile.php) | **socialnetwork.user\_profile** | Позволяет просмотреть и изменить профиль пользователя социальной сети. |
| [Профиль группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_profile.php) | **socialnetwork.group** | Для просмотра и изменения профиля группы социальной сети. |
| [Top групп](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_top.php) | **socialnetwork.group\_top** | Показывает Top групп социальной сети. |
| [Бизнес-процессы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_bizproc.php) | **socialnetwork.bizproc** | Выводит задания и историю по бизнес-процессам. |
| [Входящие сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_input.php) | **socialnetwork.messages\_input** | Показывает входящие сообщения социальной сети. |
| [Выход из группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_leave_group.php) | **socialnetwork.user\_leave\_group** | Позволяет выйти из группы социальной сети. |
| [Группы пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_groups.php) | **socialnetwork.user\_groups** | Позволяет просмотреть и изменить группы пользователя социальной сети. |
| [Запрос пользователя на вступление в группу](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_request_group.php) | **socialnetwork.user\_request\_group** | Позволяет пользователю отправить запрос на вступление в группу социальной сети. |
| [Запросы на вступление в группу (ex)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_group_requests_ex.php) | **socialnetwork.group\_requests.ex** | Позволяет показать приглашения и запросы пользователя. |
| [Запросы на вступление в группу](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_requests.php) | **socialnetwork.group\_requests** | Позволяет просмотреть и изменить запросы на вступление в группу социальной сети. |
| [Запросы пользователю](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_requests.php) | **socialnetwork.messages\_requests** | Показывает запросы пользователю социальной сети. |
| [Исходящие сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_output.php) | **socialnetwork.messages\_output** | Показывает исходящие сообщения социальной сети. |
| [Лог активности пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_log.php) | **socialnetwork.activity** | Выводит лог активности пользователя социальной сети. |
| [Лог изменений (ex)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork.log.ex.php) | **socialnetwork.log.ex** | Выводит запись вместе с комментариями. |
| [Лог изменений (entry)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_log_entry.php) | **socialnetwork.log.entry** | Получает cписок комментариев к каждой из записей социальной сети. |
| [Меню профайла группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_menu.php) | **socialnetwork.group\_menu** | Показывает меню профайла группы социальной сети. |
| [Меню профайла пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_menu.php) | **socialnetwork.user\_menu** | Показывает меню профайла пользователя социальной сети. |
| [Меню сообщений пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_menu.php) | **socialnetwork.messages\_menu** | Показывает меню сообщений пользователя социальной сети. |
| [Модераторы группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_mods.php) | **socialnetwork.group\_mods** | Служит для просмотра и изменения модераторов группы социальной сети. |
| [Настройка разрешений пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_settings_edit.php) | **socialnetwork.user\_settings\_edit** | Позволяет настраивать разрешения пользователя (приватность) социальной сети. |
| [Настройка функционала](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_features.php) | **socialnetwork.features** | Позволяет настраивать функционал пользователей и рабочих групп социальной сети. |
| [Обработка задания Бизнес-процесса](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_bizproc_edit.php) | **socialnetwork.bizproc\_edit** | Позволяет обработать задание бизнес-процесса. |
| [Переписка в виде чата](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_chat.php) | **socialnetwork.messages\_chat** | Показывает переписку в виде чата социальной сети. |
| [Переписка с пользователем](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_users_messages.php) | **socialnetwork.messages\_users\_messages** | Показывает переписку с пользователем социальной сети. |
| [Переписка с пользователями](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_messages_users.php) | **socialnetwork.messages\_users** | Показывает переписку с пользователями социальной сети. |
| [Подписка](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_subscribe.php) | **socialnetwork.subscribe** | Служит для настройки подписки социальной сети. |
| [Поиск групп](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_search.php) | **socialnetwork.group\_search** | Создает страницу поиска рабочих групп. |
| [Поиск пользователей](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_search.php) | **socialnetwork.user\_search** | Позволяет искать пользователей социальной сети. |
| [Показ событий](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_events.php) | **socialnetwork.events** | Показывает события: новое сообщение, запрос на добавление в список друзей и пр. социальной сети. |
| [Показ событий (ajax)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_events_dyn.php) | **socialnetwork.events\_dyn** | Показывает события с помощью AJAX: новое сообщение, запрос на добавление в список друзей и пр. социальной сети. |
| [Пользователи группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_users.php) | **socialnetwork.group\_users** | Служит для просмотра и изменения пользователей группы социальной сети. |
| [Пользователи группы (расширенный)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_group_users_ex.php) | **socialnetwork.group\_users.ex** | Служит для просмотра и изменения пользователей группы социальной сети. |
| [Пользователи группы (расширенный)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_user_friends_ex.php) | **socialnetwork.user\_friends.ex** | Служит для просмотра и изменения пользователей группы социальной сети. |
| [Приглашение пользователей в группу](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_request_search.php) | **socialnetwork.group\_request\_search** | Служит для приглашения пользователей в группу социальной сети. |
| [Приглашения на вступление в группу](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_requests_out.php) | **socialnetwork.group\_requests\_out** | Позволяет просмотреть и изменить приглашения на вступление в группу социальной сети. |
| [Создание группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_create.php) | **socialnetwork.group\_create** | Позволяет создать новую (редактировать уже существующую) группу социальной сети. |
| [Создание группы в попап-диалоге](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_group_iframe_popup.php) | **socialnetwork.group.iframe.popup** | Позволяет создать новую группу в попап-диалоге. |
| [Создание группы в попап-диалоге (ex)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_group_create_ex.php) | **socialnetwork.group\_create.ex** | Позволяет создать новую группу в попап-диалоге. |
| [Список подписки пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_subscribe_list.php) | **socialnetwork.subscribe\_list** | Позволяет показать список подписки пользователя социальной сети. |
| [Удаление группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_delete.php) | **socialnetwork.group\_delete** | Служит для удаления группы социальной сети. |
| [Форма отправки сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_message_form.php) | **socialnetwork.message\_form** | Позволяет отправить сообщение пользователю социальной сети. |
| [Форма приглашения пользователя вступить в группу](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_request_user.php) | **socialnetwork.group\_request\_user** | Создает форму приглашения пользователю вступить в группу социальной сети. |
| [Черный список группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_group_ban.php) | **socialnetwork.group\_ban** | Служит для просмотра и изменения черного списка группы социальной сети. |
| [Редактирование сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socialnetwork_blog_post_edit.php) | **socialnetwork.blog.post.edit** | Позволяет редактировать/создавать сообщения. |  |
| [RSS блогов](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_blog_rss.php) | **socialnetwork.blog.rss** | Выводит RSS блогов группы или сайта в заданном формате. |
| **Используются только в БУС** | | |
| [Друзья пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_friends.php) | **socialnetwork.user\_friends** | Позволяет просмотреть и изменить друзей пользователя социальной сети. |
| [Дни рождения друзей](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_birthday.php) | **socialnetwork.user\_birthday** | Выводит ближайшие дни рождения друзей пользователя социальной сети. |
| [Добавление друга](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_friends_add.php) | **socialnetwork.user\_friends\_add** | Позволяет отправить запрос на добавление друга социальной сети. |
| [Удаление друга](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_friends_delete.php) | **socialnetwork.user\_friends\_delete** | Позволяет удалить друга социальной сети. |
| [Черный список пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/socnet_user_ban.php) | **socialnetwork.user\_ban** | Служит для просмотра и изменения черного списка пользователя социальной сети. |
| **Используются только на КП** | | |
| [Живая лента (мобильная, ex)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/mobile_socialnetwork_log_ex.php) | **mobile.socialnetwork.log.ex** | Отображает Живую ленту в формате для мобильных устройств. |
| [Живая лента (мобильная)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/mobile_socialnetwork_log.php) | **mobile.socialnetwork.log** | Отображает Живую ленту в формате для мобильных устройств. |
| [Сообщение Живой ленты (мобильной)](https://dev.1c-bitrix.ru/user_help/components/obschenie/social_network/mobile_socialnetwork_log_entry.php) | **mobile.socialnetwork.log.entry** | Отображает сообщение Живой ленты в формате для мобильных устройств. |

Новинки документации в соцсетях:

© «Битрикс», 2001-2025, «1С-Битрикс», 2025

Наверх