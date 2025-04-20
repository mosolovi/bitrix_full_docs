[Форум](/api_help/forum/index.php)

Для разработчиков

Для разработчиков
=================

Перед использованием модуля **Форум** необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?
   if(CModule::IncludeModule("forum"))
   { 
      //здесь можно использовать функции модуля 
   } 
   ?>Копировать
```

Публичная часть форума строится на высокоуровневых функциях и классах ядра форума.

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Форум (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_composite.php) | **forum** | Создает полноценный публичный интерфейс форума. |
| [Помощь](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_help.php) | **forum.help** | Выводит помощь по форуму. |
| [Форумы (список)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_index.php) | **forum.index** | Выводит список всех форумов. |
| [Шаблоны](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_interface.php) | **forum.interface** | Сборник js-библиотек служебных шаблонов. |
| [Меню](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_menu.php) | **forum.menu** | Выводит меню форума. |
| [Сообщения (проверка)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_message_approve.php) | **forum.message.approve** | Выводит неодобренные сообщения форума. |
| [Сообщения (перемещение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_message_move.php) | **forum.message.move** | Служит для перемещения сообщений форума. |
| [Письмо](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_message_send.php) | **forum.message.send** | Выводит форму отправки письма (сообщения) пользователю. |
| [PM (изменение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_pm_edit.php) | **forum.pm.edit** | Служит для создания нового или редактирования существующего персонального сообщения. |
| [PM (папки)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_pm_folder.php) | **forum.pm.folder** | Выводит список личных папок пользователя. |
| [PM (список)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_pm_list.php) | **forum.pm.list** | Выводит список личных сообщений пользователя из указанной папки. |
| [PM (чтение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_pm_read.php) | **forum.pm.read** | Создает страницу детального просмотра персонального сообщения. |
| [PM (поиск)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_pm_search.php) | **forum.pm.search** | Выводит форму поиска пользователя. |
| [Форма создания сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_post_form.php) | **forum.post\_form** | Выводит форму создания сообщения (или темы) форума. |
| [RSS форума](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_rss.php) | **forum.rss** | Служит для экспорта RSS форума в указанном формате. |
| [Правила](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_rules.php) | **forum.rules** | Служит для создания страницы с правилами форума. |
| [Поиск](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_search.php) | **forum.search** | Выводит форму поиска по форумам. |
| [Статистика](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_statistic.php) | **forum.statistic** | Выводит статистику по форуму. |
| [Подписка](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_subscribe_list.php) | **forum.subscribe.list** | Выводит список подписок пользователя на сообщения и темы форумов. |
| [Темы (новые)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_active.php) | **forum.topic.active** | Выводит список новых тем форума. |
| [Темы (список внешний)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_last.php) | **forum.topic.last** | Выводит список тем (для использования вне форума). |
| [Темы (список)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_list.php) | **forum.topic.list** | Выводит список всех тем форума. |
| [Темы (перемещение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_move.php) | **forum.topic.move** | Создает страницу перемещения тем форума. |
| [Темы (создание)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_new.php) | **forum.topic.new** | Создание новой темы форума. |
| [Темы (чтение)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_read.php) | **forum.topic.read** | Выводит список сообщений темы форума. |
| [Темы (отзывы)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_reviews.php) | **forum.topic.reviews** | Выводит форму для создания отзыва к элементу инфоблока (например, новости, фотографии), а также весь список отзывов. |
| [Темы (поиск)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_topic_search.php) | **forum.topic.search** | Выводит форму поиска тем форума. |
| [Пользователь (список пользователей)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_user_list.php) | **forum.user.list** | Выводит список пользователей форума. |
| [Пользователь (сообщения)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_user_post.php) | **forum.user.post** | Выводит список сообщений, тем пользователя форума. |
| [Пользователь (изменение профиля)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_user_profile_edit.php) | **forum.user.profile.edit** | Выводит форму редактирования профиля пользователя. |
| [Пользователь (профиль)](https://dev.1c-bitrix.ru/user_help/components/obschenie/forum/forum_user_profile_view.php) | **forum.user.profile.view** | Служит для просмотра профиля пользователя форума. |

Новинки документации в соцсетях: