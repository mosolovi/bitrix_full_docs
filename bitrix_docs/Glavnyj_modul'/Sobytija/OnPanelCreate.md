[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnPanelCreate (с версии 3.0.14)

OnPanelCreate
=============

```
функция-обработчик();Копировать
```

Событие "OnPanelCreate" вызывается в момент сбора данных для [построения](/api_help/main/reference/cmain/showpanel.php) [панели управления](/api_help/main/general/panel.php) в публичной части сайта. Как правило задачи обработчика данного события - добавлять свои кнопки в панель управления сайтом.

#### Параметры

Без параметров.

#### Смотрите также

* [Панель управления](/api_help/main/general/panel.php)
* [CMain::AddPanelButton](/api_help/main/reference/cmain/addpanelbutton.php)
* [CMain::ShowPanel](/api_help/main/reference/cmain/showpanel.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример функции-обработчика:

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("main", "OnPanelCreate", Array("MyClass", "OnPanelCreateHandler"));
class MyClass
{
	// добавим кнопку в панель управления
	public static function OnPanelCreateHandler()
	{
		global $APPLICATION;
		$APPLICATION->AddPanelButton(array(
			"HREF"      => "/bitrix/admin/my_page.php", // ссылка на кнопке
			"SRC"       => "/bitrix/images/my_module_id/button_image.gif", // картинка на кнопке
			"ALT"       => "Текст всплывающей подсказки на кнопке", 
			"MAIN_SORT" => 300, 
			"SORT"      => 10
		));
	}
	/*
		Теперь при выводе панели управления в публичной части сайта
		будет также всегда выводиться наша кнопка
	*/
}
?>Копировать
```

Новинки документации в соцсетях: