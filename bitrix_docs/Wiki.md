[Wiki](/api_help/wiki/index.php)

Для разработчиков

Для разработчиков
=================

Модуль предназначен для реализации функционала Wikipedia (коллективной работы над контентом страницы).

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<? 
if(CModule::IncludeModule("wiki"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

Модуль включает в себя следующие Компоненты 2.0:

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Комплексный Wiki компонент](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki.php) | **wiki** | Комплексный компонент позволяет вести полнофункциональную работу с Wiki. |
| [Меню](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_menu.php) | **wiki.menu** | Выводит меню команд. |
| [Страница](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_show.php) | **wiki.show** | Выводит основную страницу Wiki. |
| [Редактирование](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_edit.php) | **wiki.edit** | Выводит форму редактирования страницы. |
| [Категории](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_categories.php) | **wiki.categories** | Выводит список категорий. |
| [История](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_history.php) | **wiki.history** | Выводит историю изменений страницы. |
| [Обсуждения](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_discussion.php) | **wiki.discussion** | Выводит обсуждение по статье. |
| [Сравнение версий](https://dev.1c-bitrix.ru/user_help/components/content/wiki/wiki_history_diff.php) | **wiki.history.diff** | Выводит тексты версий для сравнения. |

Новинки документации в соцсетях: