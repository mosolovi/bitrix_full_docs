[Блоги](/api_help/blogs/index.php)

Для разработчиков

Для разработчиков
=================

Перед использованием модуля необходимо проверить, установлен ли он, и подключить его при помощи конструкции:

```
<?
if (CModule::IncludeModule("blog"))
{
	//здесь можно использовать функции модуля
}
?>Копировать
```

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Блоги (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog.php) | **blog** | Создает полноценный публичный интерфейс блога. |
| [Сообщения блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_blog.php) | **blog.blog** | Выводит сообщения блога с возможностью их фильтрации по категории и дате. |
| [Черновики сообщений блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_blog_draft.php) | **blog.blog.draft** | Выводит неопубликованные сообщения текущего пользователя блога. |
| [Редактирование блога](http://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_blog_edit.php) | **blog.blog.edit** | Служит для изменения параметров и настройки блога. |
| [Лучшие сообщения блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_blog_favorite.php) | **blog.blog.favorite** | Выводит список лучших сообщения блога на основе отметок владельца блога (при создании сообщений владелец блога указывает индекс сортировки сообщения). |
| [Календарь](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_calendar.php) | **blog.calendar** | Выводит календарь сообщений блога. |
| [Теги блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_category.php) | **blog.category** | Служит для редактирования тегов сообщений блога. |
| [Комментируемые сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_commented_posts.php) | **blog.commented\_posts** | Выводит наиболее комментируемые сообщения блогов за заданный период. |
| [Лента друзей](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_friends.php) | **blog.friends** | Выводит сообщения друзей пользователя блога. |
| [Блоги группы](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_group_blog.php) | **blog.group.blog** | Выводит блоги группы. |
| [Группы блогов](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_groups.php) | **blog.groups** | Выводит непустые группы блогов. |
| [Информация о блоге](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_info.php) | **blog.info** | Выводит информацию о блоге со списком тегов. |
| [Меню блогов](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_menu.php) | **blog.menu** | Выводит меню блога. |
| [Новые блоги](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_new_blogs.php) | **blog.new\_blogs** | Выводит новые блоги. |
| [Новые комментарии](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_new_comments.php) | **blog.new\_comments** | Выводит последние комментарии к сообщениям блогов. |
| [Новые сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_new_posts.php) | **blog.new\_posts** | Выводит последние сообщения блогов текущего сайта. |
| [Последние сообщения всех блогов](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_new_posts_list.php) | **blog.new\_posts.list** | Выводит последние сообщения блогов с постраничной навигацией. |
| [Популярные блоги](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_popular_blogs.php) | **blog.popular\_blogs** | Выводит популярные блоги. |
| [Популярные сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_popular_posts.php) | **blog.popular\_posts** | Выводит наиболее просматриваемые сообщения блогов за заданный период. |
| [Сообщение детально](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_post.php) | **blog.post** | Выводит сообщение блога подробно. |
| [Комментарии к сообщению](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_post_comment.php) | **blog.post.comment** | Выводит комментарии к сообщению блога с возможностью добавления нового комментария. |
| [Редактирование сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_post_edit.php) | **blog.post.edit** | Служит для создания новых или редактирования существующих сообщения блога. |
| [Trackback'и сообщения](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_post_trackback.php) | **blog.post.trackback** | Выводит Trackback-адрес и Trackback'и к сообщению блога. |
| [Получение Trackback'ов к сообщению](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_post_trackback_get.php) | **blog.post.trackback.get** | Получает Trackback к сообщению блога. |
| [RSS блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_rss.php) | **blog.rss** | Выводит RSS блогов в заданном формате. |
| [RSS блогов по группам/сайтам](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_rss_all.php) | **blog.rss.all** | Выводит RSS блогов группы или сайта в заданном формате. |
| [Ссылки на RSS блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_rss_link.php) | **blog.rss.link** | Выводит ссылки на RSS блога. |
| [Поиск по блогам](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_search.php) | **blog.search** | Выводит непустые группы блогов. |
| [Профиль пользователя](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_user.php) | **blog.user** | Позволяет просмотреть и изменить профиль пользователя. |
| [Группы пользователей блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_user_group.php) | **blog.user.group** | Служит для редактирования группы пользователей блога. |
| [Настройка пользователей блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_user_settings.php) | **blog.user.settings** | Позволяет настраивать пользователей блога: добавлять их в друзья, удалять. |
| [Настройка прав пользователя блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_user_settings_edit.php) | **blog.user.settings.edit** | Позволяет настраивать привязку пользователя к группам блога. |
| [Получение данных в формате metaWeblog](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_metaweblog.php) | **blog.metaweblog** | Осуществляет импорт в формате MetaWeblog. |
| [Неопубликованные сообщения блога](https://dev.1c-bitrix.ru/user_help/components/obschenie/blogs/blog_moderation.php) | **blog.blog.moderation** | Выводит сообщения блога, требующие модерации. |

Новинки документации в соцсетях: