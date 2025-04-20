[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAdminContextMenuShow (с версии 9.5.10)

OnAdminContextMenuShow
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
Handler(
	array &items
);Копировать
```

Событие OnAdminContextMenuShow вызывается в функции [CAdminContextMenu::Show()](/api_help/main/general/admin.section/classes/cadmincontextmenu/show.php) при выводе в административном разделе панели кнопок. Событие позволяет модифицировать или добавить собственные кнопки на панель.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| **items** | Ссылка на массив кнопок на панели. Структура массива описана на странице [Конструктор CAdminContextMenu](/api_help/main/general/admin.section/classes/cadmincontextmenu/cadmincontextmenu.php). |

#### Возвращаемое значение

Возвращаемое значение не используется.

#### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Класс CAdminContextMenu](/api_help/main/general/admin.section/classes/cadmincontextmenu/index.php)

### Примеры использования

```
<?
AddEventHandler("main", "OnAdminContextMenuShow", "MyOnAdminContextMenuShow");
public static function MyOnAdminContextMenuShow(&$items)
{
	//add custom button to the index page toolbar
	if($GLOBALS["APPLICATION"]->GetCurPage(true) == "/bitrix/admin/index.php")
		$items[] = array("TEXT"=>"Настройки модулей", "ICON"=>"", "TITLE"=>"Страница настроек модулей", "LINK"=>"settings.php?lang=".LANGUAGE_ID);
}
?>Копировать
```

Новинки документации в соцсетях: