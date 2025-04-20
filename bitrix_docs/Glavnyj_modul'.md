[Главный модуль](/api_help/main/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Компоненты

### Описание

Раздел предназначен для технических специалистов со знанием PHP и HTML. Раздел содержит сведения о технологиях и основных принципах, заложенных в систему **Bitrix Framework**, описание классов и функций модуля **Главный модуль**.

Документация носит справочный характер. Для дополнительного изучения рекомендуются учебные курсы [Администратор. Базовый](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=35&CHAPTER_ID=04493) и [Разработчик Bitrix Framework](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43).

Смотрите также:

* [Пользовательская документация по Главному модулю](http://dev.1c-bitrix.ru/user_help/settings/index.php)

### Компоненты

Модуль включает в себя следующие Компоненты 2.0:

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Рабочий стол](https://dev.1c-bitrix.ru/user_help/description_decisions/state/official_site/components/gosportal_desktop.php) | **desktop** | Позволяет создать настраиваемый рабочий стол с использованием разнофункциональных гаджетов. |
| [Упрощенный HTML-редактор](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/fileman_light_editor.php) | **fileman.light\_editor** | Выводит упрощенный визуальный HTML-редактор. |
| [Элемент управления "Календарь"](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/main_calendar.php) | **main.calendar** | Используется для ввода даты/времени. |
| [Элемент управления "Часы"](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/main_clock.php) | **main.clock** | Служит для удобного ввода времени с использованием часов. |
| [Элемент управления "Палитра"](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/main_colorpicker.php) | **main.colorpicker** | Служит для удобного ввода таблицы выбора цвета. |
| [Журнал изменений](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/event_list.php) | **event\_list** | Позволяет вывести историю изменений, произошедших на проекте. |
| [Форма обратной связи](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/main_feedback.php) | **main.feedback** | Выводит форму для отправки сообщения с сайта на E-mail. |
| **Включаемые области** | | |
| [Вставка включаемой области](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/included_regions/main_include.php) | **main.include** | Располагается в шаблоне дизайна сайта и определяет место расположения включаемых областей страниц и разделов. |
| **Навигация** | | |
| [Выбор сайта](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/navigation/main_site_selector.php) | **main.site.selector** | Включен в шаблон дизайна сайта и служит для переключения между сайтами, созданными на базе данной копии продукта. |
| [Меню](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/navigation/menu.php) | **menu** | Выводит меню указанного типа. |
| [Навигационная цепочка](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/navigation/breadcrumb.php) | **breadcrumb** | Выводит навигационную цепочку в шаблоне. |
| [Пункты меню](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/navigation/menu_section.php) | **menu.sections** | Осуществляет дополнение созданного меню названиями разделов инфоблоков. |
| **Карта сайта** | | |
| [Карта сайта](https://dev.1c-bitrix.ru/user_help/components/content/sitemap/main_map.php) | **main.map** | Осуществляет отображение карты сайта. |
| **Пользователи** | | |
| [Имя пользователя с тултипом](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/user/main_user_link.php) | **main.user.link** | Выводит имя пользователя с всплывающей подсказкой (тултипом), который содержит информацию о пользователе социальной сети.. |
| [Настраиваемая регистрация](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/user/main_register.php) | **main.register** | Позволяет настроить форму регистрации на сайте. |
| [Параметры пользователя](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/user/main_profile.php) | **main.profile** | Выводит в публичную часть сайта информацию о пользователе. |
| [Форма авторизации](http://dev.1c-bitrix.ru/user_help/settings/users/components_2/system_auth_form.php) | **system.auth.form** | Выводит форму авторизации. |
| [Форма подтверждения регистрации](https://dev.1c-bitrix.ru/user_help/components/sluzhebnie/user/system_auth_confirmation.php) | **system.auth.confirmation** | Выводит форму подтверждения регистрации. |
| **Системные компоненты (не описываются)** | | |
| Форма авторизации | **system.auth.authorize** | Осуществляет вывод формы авторизации. |
| Форма смены пароля | **system.auth.changepasswd** | Осуществляет вывод форма смены пароля. |
| Форма отправки контрольного слова для смены пароля | **system.auth.forgotpasswd** | Осуществляет вывод форма отправки контрольного слова для смены пароля. |
| Форма регистрации | **system.auth.registration** | Осуществляет отображение формы регистрации. |
| Форма ввода настраиваемого пользовательского свойстства | **system.field.edit** | Осуществляет ввод настраиваемого пользовательского свойства. |
| Форма вывода настраиваемого пользовательского свойстсва | **system.field.view** | Осуществляет вывод настраиваемого пользовательского свойства. Чтобы не использовать API классов пользовательских полей для получения значений, можно использовать этот компонент:  ``` $arUserFields = $GLOBALS["USER_FIELD_MANAGER"]->GetUserFields("IBLOCK_30_SECTION", 144, LANGUAGE_ID); foreach ($arUserFields as $FIELD_NAME => $arUserField): 	$APPLICATION->IncludeComponent( 		"bitrix:system.field.view", 		$arUserField["USER_TYPE"]["USER_TYPE_ID"], 		array("arUserField" => $arUserField), null, array("HIDE_ICONS"=>"Y") 	); endforeach;Копировать ```   Где:   IBLOCK\_30\_SECTION - объект (группа инфоблока 30)  144 - ID группы. |
| Шаблон постраничной навигации | **system.pagenavigation** | шаблон постраничной навигации. |
| Форма вывода сообщения об ошибке | **system.show\_message** | Осуществляет вывод сообщения об ошибке. |
| Компонент вывода формы | **main.interface.form** | Осуществляет вывод форм в рамках универсальных списков. |
| Компонент вывода таблицы | **main.interface.grid** | Осуществляет вывод таблиц в рамках универсальных списков. |
| Компонент вывода панели инструментов | **main.interface.toolbar** | Осуществляет вывод панели инструментов в рамках универсальных списков. |
| Компонент вывода кнопок меню | **main.interface.buttons** | Осуществляет вывод своего [меню на странице](https://dev.1c-bitrix.ru/community/blogs/antonds/make-your-menu-with-counters-in-bitrix24.php "Статья в блоге"). |

Новинки документации в соцсетях: